# devcontainer-java-template

mvn archetype:generate \
  -DgroupId=com.sample.app \
  -DartifactId=hello \
  -DarchetypeArtifactId=maven-archetype-quickstart \
  -DarchetypeVersion=1.4 \
  -DinteractiveMode=false

mvn -f ./hello/pom.xml org.codehaus.mojo:versions-maven-plugin:2.8.1:set-property \
  -Dproperty=maven.compiler.source \
  -DnewVersion=1.8

mvn -f ./hello/pom.xml org.codehaus.mojo:versions-maven-plugin:2.8.1:set-property \
  -Dproperty=maven.compiler.target \
  -DnewVersion=1.8


mvn -f ./hello/pom.xml package

java -cp ./hello/target/hello-1.0-SNAPSHOT.jar com.sample.app.App
