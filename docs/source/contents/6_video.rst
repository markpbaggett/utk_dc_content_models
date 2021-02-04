Video
=====

About
-----

Video objects in our repository have an video content model.  The content model is used to preserve video files and
serve them in a player.

As of February 4, 2021, the Libraries has :code:`96` video objects.

The Model and Its Binaries
--------------------------

A standard video object looks like this:

.. image:: ../images/video.png

* **RELS-EXT** explains what the object is and how it relates to other objects in the repository.  The file is written in RDF XML and always describes its relationships to other digital objects it is a part of.
* **OBJ** is the preservation object. This is the most critical binary here.
* **MODS** contains our descriptive metadata.  Its relationship to RDF and linked data is described in our `https://utk-mods-to-rdf.readthedocs.io/en/latest/>`_.
* **DC** is generated from our **MODS** on ingest based on a transform we supply.  It is useful to the current Fedora API but is not significant for migration.
* **TN** a thumbnail.  Since this is sometime not generated, it is significant to migration.
* **MP4** is an access proxy that is intended to be played in the player.  Sometimes this is generated from the OBJ, but not in all cases.  For this reason, it is significant to migration.
* **TECHMD** is a FITS generated XML file based on the preservation object (OBJ). Ideally, this would be triples in a :code:`fedora:Resource` (maybe on the file rather than the object) in our next system.


Identifying via RELS-EXT
------------------------

A standard video object has RDF that states the collection(s) to which it belongs and its content model:

.. code-block:: turtle
    :emphasize-lines: 6

    @prefix ns0: <info:fedora/fedora-system:def/relations-external#> .
    @prefix ns1: <info:fedora/fedora-system:def/model#> .

    <info:fedora/wderfilms:10>
      ns0:isMemberOfCollection <info:fedora/gsmrc:wderfilms> ;
      ns1:hasModel <info:fedora/islandora:sp_videoCModel> .

A video object always has a triple that states it has a
:code:`<info:fedora/fedora-system:def/model#hasModel>` of :code:`info:fedora/islandora:sp_videoCModel`.
