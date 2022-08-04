---
slide: 04-methods
---

{:.text-tomato}
### Parámetros por defecto

<pre>
  <code class="language-ruby">
   def take_vacations(days = 15, *options)
    print options
   end
   </code>
</pre>