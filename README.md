The official website is [http://pugixml.org/](http://pugixml.org/).

Basic Usage: (From official documentation)

```
// You can use load_buffer_inplace to load document from mutable memory block; the block's lifetime must exceed that of document
char* buffer = new char[size];
memcpy(buffer, source, size);

// The block can be allocated by any method; the block is modified during parsing
pugi::xml_parse_result result = doc.load_buffer_inplace(buffer, size);

// You have to destroy the block yourself after the document is no longer used
delete[] buffer;
```


```
pugi::xpath_node_set imgs = doc.select_nodes("//Image");
for (pugi::xpath_node_set::const_iterator it = imgs.begin(); it != imgs.end(); ++it)
{
    pugi::xpath_node node = *it;
    float XPos = node.node().attribute("XPos").as_float();
...
}
```
