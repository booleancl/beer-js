---
slide: 03-basics
---
### Blocks

- Funciones anónimas que se pasan a otros métodos
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
