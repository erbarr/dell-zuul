An ansible role to configure services to use mirrors.

**Role Variables**

.. zuul:rolevar:: mirror_fqdn
   :default: {{ zuul_site_mirror_fqdn }}

   The base host for mirror servers.

.. zuul:rolevar:: mirror_use_ssl
   :default: False

   Use ssl to communicate to mirror endpoints. Note if the platform
   cannot use ssl (for example Ubuntu Xenial apt needs additional packages)
   this will still use http instead of https when set for that platform.

.. zuul:rolevar:: pypi_fqdn
   :default: {{ mirror_fqdn }}

   The base host for PyPi mirror server.

.. zuul:rolevar:: pypi_mirror

   URL to override the generated pypi mirror url based on
   :zuul:rolevar:`configure-mirrors.pypi_fqdn`.

.. zuul:rolevar:: set_apt_mirrors_trusted
   :default: False

   Set to True in order to tag APT mirrors as trusted, needed
   when accessing unsigned mirrors with newer releases like
   Ubuntu Bionic.
