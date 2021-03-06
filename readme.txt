======================================================================
SPRING ROO WRAPPING REPOSITORY
======================================================================

This Git repository contains various script files that enable easy
production of OSGi-compliant bundles using a technique known as
"wrapping". These are generally used by Spring Roo and its add-ons.

You can read more about Spring Roo at the following location:

   http://www.springsource.org/roo

======================================================================
PREREQUISITES
======================================================================

In order to complete these instructions, you must have rights to
deploy files to http://spring-roo-repository.springsource.org/release.
All wrapped JARs are deployed under the following directory:

   /release/org/springframework/roo/wrapping

To perform wrapping you need:

 * A proper installation of Java 6 or above
 * Maven 3.0.1+ properly installed and working with your Java 5+
 * Internet access so that Maven can download required dependencies
 * Upload privileges to the above location
 * GPG setup (see main Spring Roo readme.txt for instructions)
 
 If you want to host an OSGi-compliant jar that
 does not need wrapping at http://spring-roo-repository.springsource.org/release,
 be sure to create an asc file of the jar and pom.xml using 
 gpg --ab <filename> and upload the asc files as well.

======================================================================
GIT POLICIES
======================================================================

The same Git policies apply to this repository as the normal Roo
repository.

======================================================================
RELEASING
======================================================================

The wrapping repository is separated from the normal Roo repository so
that each project in the wrapping repository can be released as part
of its own release cycle. The wrapping projects are NOT released
during the normal Roo release cycle and the Roo CI server does NOT
perform any wrapping module releases.

As such, it is expected that developers wishing to make wrapped JAR
available will manually produce/edit the relevant subdirectory of the
wrapping JAR and then use:

   mvn clean deploy

IMPORTANT: Ensure you increment the final three-digit prefix for the
version number displayed in the pom.xml. Also ensure you edit the
main Roo pom.xml <dependencyManagement> section to refer to the new
version once you have completed the deployment. This ensures everyone
is on the latest release you have made.

======================================================================
HELP
======================================================================

If you have general questions on Roo's wrapping approach, please use
the Spring Roo Community Forum. You can access the Community Forum at
http://forum.springsource.org/forumdisplay.php?f=67. Thanks for your
interest in Spring Roo!

