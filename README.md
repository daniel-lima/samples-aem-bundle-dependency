[AEM Samples] Bundle Dependency
========

This project demonstrates possible dependency issues when using OSGi bundles and how to solve them.
For further information, please refer to [Resolving OSGi bundle dependencies](http://danielhalima.com/aem/2016/12/18/resolving-osgi-bundle-dependencies/).

Requirements
------------

- AEM 6.1
- [Apache Maven](https://maven.apache.org/) version `>=3.3.9`

Building
--------

The project is based on [multimodule-content-package-archetype](https://docs.adobe.com/docs/en/aem/6-1/develop/dev-tools/vlt-mavenplugin.html#multimodule-content-package-archetype), so it has the same profiles and properties. Some common commands:

From the root directory, run ``mvn -PautoInstallPackage clean install`` to build the bundle and content package and install to a CQ instance.

From the bundle directory, run ``mvn -PautoInstallBundle clean install`` to build *just* the bundle and install to a CQ instance.

Using with VLT
--------------

To use vlt with this project, first build and install the package to your local CQ instance as described above. Then cd to `content/src/main/content/jcr_root` and run

    vlt --credentials admin:admin checkout -f ../META-INF/vault/filter.xml --force http://localhost:4502/crx

Once the working copy is created, you can use the normal ``vlt up`` and ``vlt ci`` commands.

Specifying CRX Host/Port
------------------------

The CRX host and port can be specified on the command line with:
mvn -Dcrx.host=otherhost -Dcrx.port=5502 <goals>


