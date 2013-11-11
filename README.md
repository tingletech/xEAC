xEAC
====

xEAC is an open-source [XForms](http://en.wikipedia.org/wiki/XForms)-based application for creating and managing EAC-CPF collections.  The XForms backend allows editing of the XML documents in a web form, and relationships between source and target entities are maintained automatically.  That is to say, when a CPF relation is added into the source document which points to another entity within the same system, the target document is updated to insert a CPF relation back to the source.  The xlink:arcrole for these CPF relations is controlled by an ontology manager which handles reciprocal relationships: enabling the user to designate childOf as the inverse of parentOf.  Furthermore, the xEAC editing interface interacts with a variety of REST APIs to enhance authority control and context within the record through [DBPedia](http://dbpedia.org), [VIAF](http://viaf.org), [Geonames](http://www.geonames.org), and the [Pleiades Gazetteer of Ancient Places](http://pleiades.stoa.org).  Entities which link to concepts defined on [nomisma.org](http://nomisma.org) may incorporate SPARQL queries to extract thumbnail images of related coins.  More APIs will be incorporate eventually.

The public interface includes a simple search/faceted browse, an Atom feed, and RDF and KML serializations.  KML is generated by places which link to Geonames and Pleiades URIs, and in conjunction with standard dates, the interface enables the generation of maps and timelines through the Timemap Javascript library.  The public interface will be enhanced over time.

Architecture
------------

xEAC is comprised of three server-side application which run in Apache Tomcat: [Orbeon](http://www.orbeon.com) (XForms processor), [Solr](http://lucene.apache.org/solr/) (search index used for publication), and [eXist](http://exist-db.org/exist/apps/homepage/index.html) (XML database).  XForms submissions allow these three applications to communicate through REST.

Installation and Use
--------------------

Installation and usage instructions may be found in the xEAC wiki, hosted by the American Numismatic Society: [http://wiki.numismatics.org/xeac:xeac](http://wiki.numismatics.org/xeac:xeac)

Future Work
-----------

It must be stressed the xEAC is still beta software.  While the majority of EAC-CPF elements can be edited within the form, not all attributes are available for editing.  Development has focused mainly on those attributes which correspond to linking entities together (xlink attributes within CPF relation) and standard dates.  Future work includes:

* Finish form: Represent all EAC-CPF elements and attributes
* Test for scalability
* Interface with more APIs
* Improve public interface, especially searching and browsing
* Incorporate social network graph visualization (see SPARQL, below)
* Follow evolving best practices in RDF/linked open data
* Employ SPARQL endpoint for more sophisticated querying and visualization (?)

More Information
-----------------
The EADitor blog contains information about the use of XForms work in archives in general (including xEAC) and specific implementations at the American Numismatic Society: [http://eaditor.blogspot.com/](http://eaditor.blogspot.com/).

[Building Interlinked Prosopographies: A New Approach](http://www.slideshare.net/ewg118/marac-2013), presented at MARAC Fall 2013, Philadelphia.

[Demo](http://admin.numismatics.org/xeac/) of the user interface.  To view the editing interface, please contact me for the URL and authentication credentials.  This server is not powerful enough to open the backend to numerous concurrent users.


