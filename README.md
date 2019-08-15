# topo-digraph-xml
This is a tiny Rust crate that simply defines a set of structures for
deserializing the XML definition of a libopo Directed Graph topology.

Today this XML is produced by either running  ```/usr/lib/fm/fmd/sastopo -x``` on SmartOS
or by leveraging the topo_digraph_serialize() interface in libtopo.

**NOTE**: Both the ```sastopo``` tool and the ```topo_digraph_serialize()``` interface
are only available in the development "sastopo" branch of
[git://github.com/joyent/illumos-joyent](git://github.com/joyent/illumos-joyent).

