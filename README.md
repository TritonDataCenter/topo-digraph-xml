# topo-digraph-xml
This is a tiny Rust crate that simply defines a set of structures for
deserializing the XML definition of a libopo Directed Graph topology.

Today this XML is produced by either running  ```/usr/lib/fm/fmd/sastopo -x``` on SmartOS
or by leveraging the topo_digraph_serialize() interface in libtopo.

**NOTE**: Both the ```sastopo``` tool and the ```topo_digraph_serialize()``` interface
are only available in the development "sastopo" branch of
[git://github.com/joyent/illumos-joyent](git://github.com/joyent/illumos-joyent).

To use this crate in a Rust project, specify the following in the [dependencies] section of Cargo.toml:

```
topo_digraph_xml = { git = "https://github.com/joyent/topo-digraph-xml" }
```



Sample Usage:

```
#[macro_use]
extern crate serde_derive;
extern crate serde;
extern crate serde_xml_rs;

extern crate topo_digraph_xml;
use topo_digraph_xml::{
    TopoDigraphXML,
};

fn main() {
    let xml_contents = fs::read_to_string("file.xml")?;
    let graph: TopoDigraphXML = serde_xml_rs::from_str(&xml_contents)?;

    println!("{:#?}", graph);

	Ok(())
}

```

