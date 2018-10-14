# html2dbk

Simple HTML / XHTML to DocBook converter for MarkLogic

Oliver Steele's converter is very useful, but needed a couple of small modifications to work with MarkLogic

First ensure that your HTML is well-formed XHTML:

    let $text := doc("/my/html/document.html")
    let $xhtml := xdmp:unquote(xdmp:quote($text), "http://www.w3.org/1999/xhtml", ("repair-full", "format-xml"))

Then call the main stylesheet:

    xdmp:xslt-invoke(
      '/html-to-db/html2db.xsl',
      $xhtml
    )
