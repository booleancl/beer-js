---
slide: 03-basics
---
### Constantes

- Con mayúsculas
- No deberían cambiar, ruby emite un *warning*
- `.freeze` la hace inmutable

<pre>
  <code class="language-ruby">
   URL = 'google.com'
   BaseUrl = 'buk.cl' # Permitido, pero no preferido en Buk
   BASE_URL = 'buk.cl' # Más idiomático
   AUTHOR = 'Bolean'.freeze # Inmutable
  </code>
</pre>
