BaseMaps for CKAN
============================================================================


* `Installation`_
* `Configuration`_

Installation
------------

**This plugin dependencies ckanext-spatial Plugin.**

The current version of ckanext-basemaps has been developed and tested again
**CKAN 2.1.x**. We assume a running CKAN 2.1.x instance.
※　CKAN2.3に動作可能を確認済(2015/6/19)
 
The installation has the following steps, assuming you have a running
copy of CKAN:

#. Install the extension from its source repository::

    (pyenv) $ pip install -e git+https://github.com/gsi-cyberjapan/ckanext-basemaps#egg=ckanext-basemaps


Configuration
-------------

These are the configuration options used by the extension 

#. Map Names::

    ckanext.basemaps.laylers.names = 地理院地図（標準）, 地理院地図（白地図）,電子国土基本図（オルソ画像）

#. Map URLs::

    ckanext.basemaps.laylers.urls = http://cyberjapandata.gsi.go.jp/xyz/std/{z}/{x}/{y}.png, http://cyberjapandata.gsi.go.jp/xyz/blank/{z}/{x}/{y}.png, http://cyberjapandata.gsi.go.jp/xyz/ort/{z}/{x}/{y}.jpg

#. Attributions::

    ckanext.basemaps.laylers.attributions = 国土地理院,国土地理院,国土地理院

#. plugins::

    ckan.plugins = ... spatial_metadata spatial_query mapbases_layer


#. HTML::
./src/ckan/ckan/templates/package/search.htmlの70行目に以下の内容を追加する。

    {% snippet "basemaps/snippets/tile_resource.html" %}

