---
slide: 03-basics
---
### Module Enumerable

- Provee a las clases que lo implementan con métodos para recorrer la instancia
- También entrega métodos para 
- `{}` ó  `do...end`

<pre>
  <code class="language-ruby">
   10.times { |num| puts "El número #{num}"}

   (0..10).each do |num|
     puts "El número #{num}"
   end
  </code>
</pre>
<small>Reference Eloquent Ruby</small>
