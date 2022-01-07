# Sites Products Starter - Site Entity Implementation

This repo contains an implementation of site attributes via _Streams_, instead of _global.json_. On the Knowledge Graph side, this was accomplished by:
1. Creating a [site entity](https://www.yext.com/s/3521131/entity/edit3?entityIds=27957663)
2. Adding a custom field (_c_relatedSite_) to the product entity type that relates the product with the site entity ([example](https://www.yext.com/s/3521131/entity/edit3?entityIds=24933472))
3. Converting all static pages in the repo to stream-based pages

Typically by convention, all pages in Sites starter repos are divided into two directories - based on whether or not they rely on Streams:
- **/pages** - (holds static pages - e.g. index, about, etc.)
- **/templates** - (page templates for entity pages - e.g. location, product, faq, etc.)

This repo differs in that:
- all static pages defined in the /pages directory now rely on a Stream scoped to this [saved filter](https://www.yext.com/s/3521131/entities2#p0=entity&p1=contains&p2=YFW&p3=&p0=entity-type&p1=is&p2=88384&p3=&selectedSavedFilterId=146039) (which contains a single site entity)
- all templates defined in /templates now include a reference to the site entity as a related field in frontmatter ([refer to line 16](https://github.com/lymarrie/sites-products-starter/blob/main/templates/product.hbs#L16))

Therefore, when a site entity is updated in KG, every single page template in the repo is affected, and therefore gets updated as a result.

The resulting deploy can be viewed in the platform [here](https://www.yext.com/s/3521131/yextsites/26614/branch/494/deploys/recent).
