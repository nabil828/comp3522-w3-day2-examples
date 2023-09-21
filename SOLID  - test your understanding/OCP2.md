Open-Closed Principle - Exercise 

Which of the following is OCP-complikant

A. 
```python
class DocumentProcessor:
    def process(self, document):
        if document.type == "XML":
            # Process XML document
            pass
        elif document.type == "json":
            # Process JSON document
            pass
        elif document.type == "html":
            # Process HTML document
            pass

class XML(DocumentProcessor):
    def __init__(self, document):
        self.type = "XML"

class JSON(DocumentProcessor):
    def __init__(self, document):
        self.type = "json"

class HTML(DocumentProcessor):
    def __init__(self, document):
        self.type = "html"
```

B. 
```python
class DocumentProcessor:
    def process(self, document):
        pass

class HTMLDocumentProcessor(DocumentProcessor):
    def process(self, document):
        # Process HTML document

class XMLDocumentProcessor(DocumentProcessor):
    def process(self, document):
        # Process XML document

class JSONDocumentProcessor(DocumentProcessor):
    def process(self, document):
        # Process JSON document

```

Answer B