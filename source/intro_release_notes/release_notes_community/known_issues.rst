.. _known_issues:

================================================================================
Known Issues
================================================================================

A complete list of `known issues for OpenNebula is maintained here <https://github.com/OpenNebula/one/issues?q=is%3Aopen+is%3Aissue+label%3A%22Type%3A+Bug%22+label%3A%22Status%3A+Accepted%22>`__.

This page will be updated with relevant information about bugs affecting OpenNebula, as well as possible workarounds until a patch is officially published.

Accounting and Showback
=======================

A bug that might lead to inaccurate hours in accounting and showback has been fixed. You can check all the information `here <https://github.com/OpenNebula/one/issues/1662>`_. But, old VMs won't be updated, so the bug might still be on those VMs.

Sunstone
========

Inputs expressing sizes (disk, memory) that have units in MB, GB or TB have a bug. Once expressed in MB, if you want to update its value you'll need to change the units to GB or TB.

Setting a password for remote connection to VNC / SPICE from a VM imported from a vCenter host is not working properly.

Conflicting RubyGems Module
============================

If your system is heavily customized and comes with newer RubyGems (with ``gem`` tool) module installed outside of the packaging system, e.g. via ``update_rubygems`` tool, the OpenNebula might fail to run due to conflicts between module versions. It's necessary to remove custom RubyGems module and fallback to using only distribution modules. Ensure your system has only a single RubyGems module version present.

The error you might experience:

.. code-block:: bash

    # onevm list --version
    /usr/share/rubygems/rubygems.rb:11: warning: already initialized constant Gem::VERSION
    /usr/local/share/ruby/site_ruby/rubygems.rb:13: warning: previous definition of VERSION was here
    /usr/share/rubygems/rubygems/compatibility.rb:13: warning: already initialized constant Gem::GEM_PRELUDE_SUCKAGE
    /usr/local/share/ruby/site_ruby/rubygems/compatibility.rb:14: warning: previous definition of GEM_PRELUDE_SUCKAGE was here
    /usr/share/rubygems/rubygems/compatibility.rb:34: warning: already initialized constant Gem::RubyGemsVersion
    /usr/local/share/ruby/site_ruby/rubygems/compatibility.rb:34: warning: previous definition of RubyGemsVersion was here
    /usr/share/rubygems/rubygems/compatibility.rb:36: warning: already initialized constant Gem::RbConfigPriorities
    /usr/local/share/ruby/site_ruby/rubygems/compatibility.rb:38: warning: previous definition of RbConfigPriorities was here
    /usr/share/rubygems/rubygems/compatibility.rb:54: warning: already initialized constant Gem::RubyGemsPackageVersion
    /usr/local/share/ruby/site_ruby/rubygems/compatibility.rb:59: warning: previous definition of RubyGemsPackageVersion was here
    /usr/share/rubygems/rubygems/defaults.rb:2: warning: already initialized constant Gem::DEFAULT_HOST
    /usr/local/share/ruby/site_ruby/rubygems/defaults.rb:3: warning: previous definition of DEFAULT_HOST was here
    /usr/share/rubygems/rubygems.rb:115: warning: already initialized constant Gem::RUBYGEMS_DIR
    /usr/local/share/ruby/site_ruby/rubygems.rb:118: warning: previous definition of RUBYGEMS_DIR was here
    /usr/share/rubygems/rubygems.rb:120: warning: already initialized constant Gem::WIN_PATTERNS
    /usr/local/share/ruby/site_ruby/rubygems.rb:123: warning: previous definition of WIN_PATTERNS was here
    /usr/share/rubygems/rubygems.rb:129: warning: already initialized constant Gem::GEM_DEP_FILES
    /usr/local/share/ruby/site_ruby/rubygems.rb:132: warning: previous definition of GEM_DEP_FILES was here
    /usr/share/rubygems/rubygems.rb:138: warning: already initialized constant Gem::REPOSITORY_SUBDIRECTORIES
    /usr/local/share/ruby/site_ruby/rubygems.rb:142: warning: previous definition of REPOSITORY_SUBDIRECTORIES was here
    /usr/share/rubygems/rubygems.rb:1060: warning: already initialized constant Gem::MARSHAL_SPEC_DIR
    /usr/local/share/ruby/site_ruby/rubygems.rb:1368: warning: previous definition of MARSHAL_SPEC_DIR was here
    /usr/share/rubygems/rubygems/version.rb:150: warning: already initialized constant Gem::Version::VERSION_PATTERN
    /usr/local/share/ruby/site_ruby/rubygems/version.rb:157: warning: previous definition of VERSION_PATTERN was here
    /usr/share/rubygems/rubygems/version.rb:151: warning: already initialized constant Gem::Version::ANCHORED_VERSION_PATTERN
    /usr/local/share/ruby/site_ruby/rubygems/version.rb:158: warning: previous definition of ANCHORED_VERSION_PATTERN was here
    /usr/share/rubygems/rubygems/requirement.rb:19: warning: already initialized constant Gem::Requirement::OPS
    /usr/local/share/ruby/site_ruby/rubygems/requirement.rb:17: warning: previous definition of OPS was here
    /usr/share/rubygems/rubygems/requirement.rb:30: warning: already initialized constant Gem::Requirement::PATTERN_RAW
    /usr/local/share/ruby/site_ruby/rubygems/requirement.rb:30: warning: previous definition of PATTERN_RAW was here
    /usr/share/rubygems/rubygems/requirement.rb:31: warning: already initialized constant Gem::Requirement::PATTERN
    /usr/local/share/ruby/site_ruby/rubygems/requirement.rb:35: warning: previous definition of PATTERN was here
    /usr/share/rubygems/rubygems/requirement.rb:33: warning: already initialized constant Gem::Requirement::DefaultRequirement
    /usr/local/share/ruby/site_ruby/rubygems/requirement.rb:40: warning: previous definition of DefaultRequirement was here
    /usr/share/rubygems/rubygems/requirement.rb:241: warning: already initialized constant Gem::Version::Requirement
    /usr/local/share/ruby/site_ruby/rubygems/requirement.rb:299: warning: previous definition of Requirement was here
    /usr/share/rubygems/rubygems/platform.rb:181: warning: already initialized constant Gem::Platform::RUBY
    /usr/local/share/ruby/site_ruby/rubygems/platform.rb:198: warning: previous definition of RUBY was here
    /usr/share/rubygems/rubygems/platform.rb:187: warning: already initialized constant Gem::Platform::CURRENT
    /usr/local/share/ruby/site_ruby/rubygems/platform.rb:204: warning: previous definition of CURRENT was here
    /usr/share/rubygems/rubygems/specification.rb:59: warning: already initialized constant Gem::Specification::NONEXISTENT_SPECIFICATION_VERSION
    /usr/local/share/ruby/site_ruby/rubygems/specification.rb:53: warning: previous definition of NONEXISTENT_SPECIFICATION_VERSION was here
    /usr/share/rubygems/rubygems/specification.rb:82: warning: already initialized constant Gem::Specification::CURRENT_SPECIFICATION_VERSION
    /usr/local/share/ruby/site_ruby/rubygems/specification.rb:76: warning: previous definition of CURRENT_SPECIFICATION_VERSION was here
    /usr/share/rubygems/rubygems/specification.rb:88: warning: already initialized constant Gem::Specification::SPECIFICATION_VERSION_HISTORY
    /usr/local/share/ruby/site_ruby/rubygems/specification.rb:82: warning: previous definition of SPECIFICATION_VERSION_HISTORY was here
    /usr/share/rubygems/rubygems/specification.rb:106: warning: already initialized constant Gem::Specification::MARSHAL_FIELDS
    /usr/local/share/ruby/site_ruby/rubygems/specification.rb:100: warning: previous definition of MARSHAL_FIELDS was here
    /usr/share/rubygems/rubygems/specification.rb:109: warning: already initialized constant Gem::Specification::TODAY
    /usr/local/share/ruby/site_ruby/rubygems/specification.rb:109: warning: previous definition of TODAY was here
    /usr/share/rubygems/rubygems/specification.rb:111: warning: already initialized constant Gem::Specification::VALID_NAME_PATTERN
    /usr/local/share/ruby/site_ruby/rubygems/specification.rb:115: warning: previous definition of VALID_NAME_PATTERN was here
    /usr/share/rubygems/rubygems/specification.rb:1419: warning: already initialized constant Gem::Specification::DateTimeFormat
    /usr/local/share/ruby/site_ruby/rubygems/specification.rb:1764: warning: previous definition of DateTimeFormat was here
    Error: wrong number of arguments (0 for 1)

vCenter
=======================

There is a bug that doesn't allow to retrieve vcenter networks when vCenter server is in version 6.0

IMPORTANT!: If you are using vCenter 6.0 or below, we recommend not to upgrade to OpenNebula 5.12 and upgrade to vCenter 6.5 or above is recommended. You can check all the information `<https://github.com/OpenNebula/one/issues/4930>`_.