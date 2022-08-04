---
slide: 03-basics
---
### Yield

- De la mano con bloques
- Ejecuta el bloque pasado como argumento

<pre>
  <code class="language-ruby">
   def logger(arg1, arg2)
    puts "Alguna información relevante"
    yield(arg1, arg2)
   end

  logger(4,2){ |n1, n2| puts(n1 + n2)}
  </code>
</pre>
<small>SaaS Book</small>
