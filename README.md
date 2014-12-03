README
======

Rails 4 application to serve OpenGeoMetadata content.

Configuration
-------------

1. Change `config/environments` to have the correct `datadir`, or leave as the default `/var/cache/opengeometadata`.
2. Clone git repos that you want to include in your server's content

For example,

    # default is Rails.application.config.datadir = '/var/cache/opengeometadata'
    cd /var/cache/opengeometadata
    git clone https://github.com/OpenGeoMetadata/edu.stanford.purl.git
    
REST API
--------

To retrieve a list of institutions available in JSON, use

    /metadata/institutions.json

To retrieve a list of layers available at an institution in JSON, use:

    /metadata/<institution>.json

To retrieve metadata for a given `institution` and `layer-id`, use:

    /metadata/<institution>/<layer-id>/default.<format>

where `format` is `xml` or `html` or `json` depending on what's available for that layer in the default metadata format (typically `iso19139`).

To retrieve a specific metadata format for a given `institution` and `layer-id`, use

    /metadata/<institution>/<layer-id>/<metadata-format>.<format>
    
where `metadata-format` is `iso19139`, `fgdc`, `mods`, `geoblacklight`, etc. and `format` is `xml` or `html`
or `json` depending on what's available for that metadata format.



    

