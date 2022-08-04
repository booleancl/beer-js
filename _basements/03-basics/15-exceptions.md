---
slide: 03-basics
---
### Exceptions

- Son instancias de la clase Exception o una subclase.
- `begin`, `rescue`  `end`
- Directamente al final del método con `rescue`

<pre>
  <code class="language-ruby">
   def to_the_moon
     begin
        star_engine
     rescue
        puts "Couldn't start engine"
        return false
     end
     max_power
   end
  </code>
</pre>
<small>Reference Eloquent Ruby</small>
