[[Tema 7-Frontend de una tienda de comercio electrónico]]
$\space$
## 1.React Intl
Para internacionalizar el frontend se usa React Intl. Proporciona ciertos componentes que permiten internacionalizar mensajes, cantidades numéricas y fechas. Por ejemplo:
+ FormattedMessage
+ FormattedNumber
+ FormattedDate
+ FormattedTime
$\space$
### 1.1.Inicialización

```javascript
// src/main.jsx
const {locale, messages} = initReactIntl();  // devuelve el locale del navegador y un objeto con los mensajes correspondientes

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <Provider store={store}>
      <IntlProvider locale={locale} messages={messages}>
        <BrowserRouter>
          <App/>
        </BrowserRouter>
      </IntlProvider>
    </Provider>
  </React.StrictMode>
);
```

La función `initReactIntl()` devuelve el locale del navegador y un objeto con los mensajes correspondientes al idioma. `IntlProvider` inyecta el locale a los componentes hijos.

Los ficheros de mensajes se encuentran en `src/i18n/messages`. Están disponibles en gallego, castellano e inglés.
$\space$
### 1.2.Ejemplos
Veamos algunos componentes internacionalizados
$\space$
#### 1.2.1.Ejemplo 1: cantidades monetarias

```javascript
// ProductDetails.jsx
<p className="card-text font-weight-bold">  
    <FormattedMessage id='project.global.fields.price'/>{': '}  
    <FormattedNumber value={product.price} style="currency" currency="EUR"/>  
</p>
```
$\space$
#### 1.2.2.Ejemplo 2: fechas

```javascript
//Orders.jsx
<td><OrderLink id={order.id}/></td>  
<td>  
    <FormattedDate value={new Date(order.date)}/> - <FormattedTime value={new Date(order.date)}/>  
</td>
```
