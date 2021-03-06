Role jenkins/deploy
===================

Deploy the jenkins webapp into a application server. Currently only `apache tomcat`_ is supported.

The application server is *not* started after dropping jenkins. Neither is it stopped before doing that.

It will download and drop jenkins into the tomcat at *catalina_base*.

.. ansible:role:: jenkins/core

   :become: No
   :default jenkins_download_mirror: Mirror to download from (default: http://mirrors.jenkins-ci.org/war)
   :default jenkins_deploy_default_context_path: Apache tomcat context path (default: `"jenkins"`).

   :param version: Jenkins version to install (eg. 1.643)
   :param checksum: Checksum for the jenkins archive (eg. 4b7ba7a5af0a5c395c0740fc011b59d1)
   :param catalina_base: Tomcat instance to install into.
   :param jenkins_home: Jenkins instance home.
   :param context_path: Apache tomcat context path (default: `"{{jenkins_deploy_default_context_path}}"`)
   :param cache_directory: Where to cache downloaded artifacts for future reuse on play host.

   The `context_path` becomes part of your jenkins url. Change to ROOT to deploy it at the top-level.

.. include:: ../../_references.txt

