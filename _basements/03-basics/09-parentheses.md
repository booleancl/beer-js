---
slide: 03-basics
---
### Parentheses

- Casi siempre opcionales
- Usarlos si mejoran la legibilidad

<pre>
  <code class="language-ruby" data-line-numbers="2-4|6|7|9-11|13-15">
   def format_document(document, format)
    ...    
   end

   format_document(cv, :pdf)
   format_document book, :epub # Correcto, pero poco legible

   def words
    @content.split
   end

   if words.size > 1000
    puts 'Long document'
   end
  </code>
</pre>
<small>Reference Eloquent Ruby</small>
