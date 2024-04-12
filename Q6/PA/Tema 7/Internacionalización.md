[[Tema 7-Frontend de una tienda de comercio electrónico]]

## 1.React Intl
Usaremos React Intl para internacionalizar el frontend. Proporciona ciertos componentes para internacionalizar mensajes, cantidades numéricas y fechas como:
+ FormattedMessage
+ FormattedNumber
+ FormattedDate
+ FormattedTime

### 1.1.Inicialización

```javascript
/* Configure i18n. */  
const {locale, messages} = initReactIntl();

/* Render application. */
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

La función `initReactIntl()` devuelve el locale del navegador y un objeto con los mensajes correspondientes al idioma. `IntlProvider` inyecta el locale a los componentes hijo.

Los ficheros de mensajes se encuentran en `src/i18n/messages`. Están disponibles en gallego, castellano e inglés.

### 1.2.Ejemplos
#### 1.2.1.Ejemplo 1

