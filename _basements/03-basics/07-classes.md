---
slide: 03-basics
---
### Classes

- UpperCamelCase
- Ruby crea constantes con los nombres de las clases

<pre>
  <code class="language-ruby" data-line-numbers="2|3|5-9|11-13|15-17">
   class Document
    attr_accessor :title, :author, :content

    def initialize(title, author, content)
      @title = title
      @author = author
      @content = content
    end

    def words
      @content.split
    end

    def word_count
      words.size
    end
   end
  </code>
</pre>
<small>Reference Eloquent Ruby</small>
