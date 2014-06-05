This module provides encryptable properties within alfresco. 
This requires the use of jasypt-1.9 which can be downloaded from
http://sourceforge.net/project/showfiles.php?group_id=183612 and requires the core and
spring3 jars (current Spring version used in Alfresco 4.0)
jasypt-1.9.0.jar, jasypt-spring3-1.9.0.jar

  1. Install the alfresco-jasypt.amp

  2. Use the included extension/alfresco-encrypted.properties, extension/encrypted-properties-context.xml within
  the typical Tomcat shared classloader for alfresco.
  
  3. Apply the encryption password into environment variable to be used in XML
  configuration file
  
  4. Reference http://www.jasypt.org/cli.html in order to encrypt the value so you can use it in step 5.
  
  5. Edit the $ALFRESCO_HOME/tomcat/shared/classes/alfresco/extension/alfresco-encrypted.properties
  file to replace the key:value
  db.password.enc=ENC(<MY_ENCRYPTED_VALUE>)
  
  You can find encryption and documentation on Jasypt at:
  http://www.jasypt.org
  
You can add additional bean overrides that use property placeholders to encrypt other passwords
and properties for dependencies used by Alfresco.  You can reference a new property, typically this pattern
works well: originalproperty.enc and modify the bean property value placeholder with this
key.  You can then add this key to the alfresco-encrypted.properties to store all the
encrypted properties in one place.
