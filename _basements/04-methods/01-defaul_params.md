---
slide: 04-methods
---

{:.text-tomato}
### Parámetros por defecto

<pre>
  <code class="language-ruby">
   def take_vacations(days = 15)
    # ...
   end

   def take_vacations(days = 15, bonus = calc_bonus(days))
    # ...
   end
  </code>
</pre>