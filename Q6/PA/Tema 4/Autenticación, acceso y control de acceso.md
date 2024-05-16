[[Tema 4-Capa de servicios REST con Spring]]
$\space$
## 1.Paso seguro del ID del usuario
Algunas peticiones necesitan el ID del usuario. Es necesario poder enviarlo de forma segura del frontend al backend.

![[esquema autenticacion.png]]

Autenticarse consiste en introducir usuario y contraseña. Si es correcto devuelve una lista de caracteres, un token, que se devuelve al backend y autoriza al usuario para hacer peticiones. Este incluye el id del usuario.

Todas las peticiones que requieran el id del usuario tienen que incluir el token. Cuando se hace una petición se hace el control de acceso. Consiste en validar el token y comprobar que el usuario tiene permitido realizar esa petición.
$\space$
## 2.JWT (JSON Web Token)
Para generar los token se usan JSON Web Token. Define un formato que permite transmitir información en JSON entre dos partes de forma segura. 

Los token están formados por cabecera.cuerpo.firma:
+ **Cabecera:** tipo de token y algoritmo de firma usado codificado en base64url.
+ **Cuerpo:** información sobre una entidad codificado en base64url.
+ **Firma:** algoritmo de firma para la cabecera y el cuerpo en conjunto en base64url.

![[jwt.png]]

![[jwt 2.png]]
$\space$
### 2.1.Autenticación
Para autorizar a un usuario se recupera a partir del `userName`. Se cifra la contraseña introducida y se comprueba si coincide con `user.getPassword()`.
$\space$
### 2.2.Autorización
Se genera un token firmado con un algoritmo de firma simétrico. En el cuerpo del token se incluyen la fecha de expiración del token, el ID del usuario y el rol del usuario.
$\space$
### 2.3.Control de acceso

![[jwt3.png]]

El control de acceso se maneja con Spring Security. Permite realizarlo de forma declarativa mediante anotaciones, ficheros de configuración o código. Se hace en la clase `SecurityConfig`.

```java
@Configuration  
@EnableWebSecurity  
public class SecurityConfig {  
    @Autowired  
    private JwtGenerator jwtGenerator;  

    @Bean  
    public SecurityFilterChain securityFilterChain(HttpSecurity http) throws Exception {  
        http.cors(Customizer.withDefaults())  
            .csrf((csrf) -> csrf.disable())  
            .sessionManagement((sessionManagement) -> sessionManagement.sessionCreationPolicy(SessionCreationPolicy.STATELESS))  
            .addFilterBefore(new JwtFilter(jwtGenerator), UsernamePasswordAuthenticationFilter.class)  
            .authorizeHttpRequests((authorize) -> authorize  
                .requestMatchers(HttpMethod.POST, "/users/signUp").permitAll()  
                .requestMatchers(HttpMethod.POST, "/users/login").permitAll()  
                .requestMatchers(HttpMethod.POST, "/users/loginFromServiceToken").permitAll()  
                .requestMatchers(HttpMethod.GET, "/catalog/categories").permitAll()  
                .requestMatchers(HttpMethod.GET, "/catalog/products/*").permitAll()  
                .requestMatchers(HttpMethod.GET, "/catalog/products").permitAll()  
                .requestMatchers(HttpMethod.PUT, "/users/*").hasRole("USER")  
                .requestMatchers(HttpMethod.POST, "/users/*/changePassword").hasRole("USER")  
                .requestMatchers(HttpMethod.POST, "/shopping/shoppingcarts/*/addToShoppingCart").hasRole("USER")  
                .requestMatchers(HttpMethod.POST, "/shopping/shoppingcarts/*/updateShoppingCartItemQuantity").hasRole("USER")  
                .requestMatchers(HttpMethod.POST, "/shopping/shoppingcarts/*/removeShoppingCartItem").hasRole("USER")  
                .requestMatchers(HttpMethod.POST, "/shopping/shoppingcarts/*/buy").hasRole("USER")  
                .requestMatchers(HttpMethod.GET, "/shopping/orders/*").hasRole("USER")  
                .requestMatchers(HttpMethod.GET, "/shopping/orders").hasRole("USER")  
                .anyRequest().denyAll());  

        return http.build();  
    }  
}
```
$\space$
#### 2.3.1.Otras formas de control de acceso
Hay parte del control de acceso que no se hace en base a roles. Por ejemplo, en la búsqueda de un pedido se comprueba que el pedido además de ser de un usuario de rol `USER` pertenezca a la persona que lo busca.
