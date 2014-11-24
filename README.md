README
======

Rails 4 application to serve OpenGeoMetadata content.

Configuration
-------------

1. Change `config/development.rb` to have the correct `datadir`
2. Clone git repos that you want to include in your server's content

For example,

    Rails.application.config.datadir = /var/cache/opengeometadata
    cd /var/cache/opengeometadata
    git clone https://github.com/OpenGeoMetadata/edu.stanford.purl.git
    
REST API
--------

To retrive metadata for a given `institution` and `layer-id`

    /metadata/<institution>/<layer-id>/default[.<format>]

where `format` is `xml` or `html` depending on what's available for that layer.

To retrieve a specific metadata format, use

    /metadata/<institution>/<layer-id>/<metadata-format>[.<format>]
    
where `metadata-format` is `iso19139`, `fgdc`, `mods`, `geoblacklight`, etc. 
and `format` is `xml` or `html` depending on what's available for that layer.
You can use `metadata-format` = `default` to select the default metadata 
format for that institution.

To retrieve a list of institutions available in JSON, use

    /metadata/institutions

To retrieve a list of layers available at an institutions in JSON use:

    /metadata/<institution>


    

