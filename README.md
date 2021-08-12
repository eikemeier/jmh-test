# JMH test
Created with

    $ mvn archetype:generate \
      -DinteractiveMode=false \
      -DarchetypeGroupId=org.openjdk.jmh \
      -DarchetypeArtifactId=jmh-java-benchmark-archetype \
      -DgroupId=org.sample \
      -DartifactId=test \
      -Dversion=1.0

and added an dependency to [JOpt Simple 5.0.4](https://github.com/jopt-simple/jopt-simple/releases/tag/jopt-simple-5.0.4)

    $ mvn clean verify
    $ java -jar target/benchmarks.jar -h

results in

    Exception in thread "main" java.lang.NoSuchMethodError: 'java.util.Collection joptsimple.OptionDescriptor.options()'
	    at org.openjdk.jmh.runner.options.OptionFormatter.lineFor(OptionFormatter.java:62)
	    at org.openjdk.jmh.runner.options.OptionFormatter.format(OptionFormatter.java:51)
	    at joptsimple.OptionParser.printHelpOn(OptionParser.java:342)
	    at joptsimple.OptionParser.printHelpOn(OptionParser.java:328)
	    at org.openjdk.jmh.runner.options.CommandLineOptions.showHelp(CommandLineOptions.java:457)
	    at org.openjdk.jmh.Main.main(Main.java:46)
