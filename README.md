# impnotes
	public static void main(String[] args) {
		try {
			System.out.println(encryptString("anurag"));

			System.out.println(decryptString("YW51cmFn"));
		} catch (UnsupportedEncodingException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}

	/**
	 * decrypts a base64 encoded string
	 * 
	 * @param string
	 * @return String
	 * @throws UnsupportedEncodingException
	 */
	public static String decryptString(String string) throws UnsupportedEncodingException {
		return new String(Base64.getDecoder().decode(string), "utf-8");
	}

	/**
	 * encrypts a base64 encoded string
	 * 
	 * @param string
	 * @return String
	 * @throws UnsupportedEncodingException
	 */
	public static String encryptString(String string) throws UnsupportedEncodingException {
		return Base64.getEncoder().encodeToString(string.getBytes("utf-8"));
	}


-----------------

certificate generation---


--------------<appName> 2.0--
--generate key
openssl genrsa -out <appName>.<domainName>.key 2048

steps :
go to path :C:\rbfg\wxf
open openssl.exe on administrator mode
run above command

--generate csr using thekey
--non prod
openssl req -config C:\RBFG\WXF\openssl.cnf -out <appName>.<domainName>.csr -key <appName>.<domainName>.key -new -sha256 -nodes -subj "/C=CA/CN=<appName>.<domainName>/O=<companyName>/OU=Internal/OU=Devices/OU=NDevices"

-prod--
openssl genrsa -out <appName>.<domainName>.key 2048

openssl req -config C:\RBFG\WXF\openssl.cnf -out <appName>.<domainName>.csr -key <appName>.<domainName>.key -new -sha256 -nodes -subj "/C=CA/CN=<appName>.<domainName>/O=<companyName>/OU=Internal/OU=Devices/OU=NDevices"
	
-----------------

--jMeter command 
C:\Anurag\apache-jmeter-3.0\bin>jmeter -n -t ..\jmx-bm\bluemixLoadTest.jmx  -l test_results_20oct_21016_1216pm-2i6m.jtl
---------------------------
--Json editor and schema validator--links
http://jsonschema.net/#/
http://jsonschemalint.com/draft5/#
http://jsonlint.com/
http://json-schema-faker.js.org/#

---best for validation/formatting/and convert to xml/yml
http://jsonformatter.org/


---
-- The best link--mavem local install

http://roufid.com/3-ways-to-add-local-jar-to-maven-project/

eg:
mvn install:install-file -Dfile=C:\Anurag\Development\share-from-B\ojdbc-7.0.0.0.jar -DgroupId=oracle -DartifactId=ojdbc -Dversion=7.0.0.0 -Dpackaging=jar

--
MVN sonar

mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.1.1:sonar

---
SSL configuration

https://www.drissamri.be/blog/java/enable-https-in-spring-boot/
http://docs.spring.io/spring-boot/docs/current/reference/html/howto-embedded-servlet-containers.html

---

http://stackoverflow.com/questions/30770280/spring-boot-ssl-client

---
Two-way ssl (tls/ssl)
http://www.robinhowlett.com/blog/2016/01/05/everything-you-ever-wanted-to-know-about-ssl-but-were-afraid-to-ask/ 

wsgen - example

C:\Anurag\Development\MidTier\testSoapJavaClient>wsgen -verbose -cp ./target/classes com.rbc.midtier.HelloWorldImpl -s .
/src/main/java com/rbc/midtier
com\rbc\midtier\jaxws\GetHelloWorldAsString.java
com\rbc\midtier\jaxws\GetHelloWorldAsStringResponse.java

---

wsgen -verbose -cp ./target/classes com.rbc.midtier.proposalCalculator.ProposalInquiryWSService -s ./src/main/java com/rbc/midtier/proposalCalculator/jaxws

---
IntelliJ: Working on multiple projects

https://stackoverflow.com/questions/8774024/intellij-working-on-multiple-projects

---free intelli U activation lincense server
How to use?

   1) open the activation window
    2)choose the Activate new license with License server
    3)fill the blank with http://xidea.online
    4)NO SLASH ("/") AT THE END OF THE URL
    5)press OK
    
    #list pf license servers
http://xidea.online
http://intellij.mandroid.cn/
http://idea.imsxm.com/
http://idea.iteblog.com/key.php

-
downloadable
https://laucyun.com/jetbrains/2018.6.21
