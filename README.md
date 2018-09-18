# html2dbk
HTML to Docbook converter

Oliver Steele's converter is very useful, but needs modifications to work with MarkLogic

    xdmp:xslt-invoke(
      '/html-to-db/html2db.xsl',
      $xhtml
    )
