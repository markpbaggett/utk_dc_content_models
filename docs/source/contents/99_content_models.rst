Content Models
==============

About
-----

Each content model is represented by a Fedora object with a RELS-EXT datastream that states its a content model.

.. code-block:: turtle
    :emphasize-lines: 3

    @prefix ns0: <info:fedora/fedora-system:def/model#> .

    <info:fedora/islandora:collectionCModel> ns0:hasModel <info:fedora/fedora-system:ContentModel-3.0> .

We're not sure if these should be migrated, but assume that they should not.

As of February 4, 2021, the Libraries has :code:`24` content model objects.
