>The basic functionality for using cryptographic techniques in Java is provided by the Java Cryptography Architecture (JCA) and its sibling, the Java Cryptography Extension (JCE)
>The JCA architecture is a provider-basedarchitecture 
-It has been defined as an intermediary layer (an interface) between the Java application and the cryptography provider
>The JCA and the JCE provide a set of classes and interfaces 
-java.security, 
-javax.crypto, 
-javax.crypto.spec, 
-javax.crypto.interfaces 
>That means that the encryption is not done by the JCA, but by the provider.
>Cryptographic Service Provider (CSP) is Bouncy Castle but it is not the only one. 
>The Java JDK includes also the standard Sun or SunJCE provider which is included in the JDK Java Cryptography Architecture (JCA).
>JCA (Java Cryptography Architecture) 
-MessageDigest 
-Signature 
-KeyPairGenerator 
-KeyFactory 
-KeyStore 
-SecureRandomAlgorithmParameters 
-AlgorithmParameterGenerator 
-CertificateFactory 
-CertPathBuilder 
-CertStore 
>Package ¡°java.security¡±
>Java Cryptography Extension (JCE) 
-Cipher 
-KeyGenerator 
-SecretKeyFactory 
-KeyAgreement 
-Mac
>Package ¡°javax.crypto¡±
>Provider List 
-JAVA_HOME/lib/security/java.security (JAVA version 8.xx)
>Example 
-security.provider.1=sun.security.provider.Sun 
-security.provider.2=com.apple.crypto.provider.Apple 
-security.provider.3=sun.security.rsa.SunRsaSign 
-security.provider.4=com.sun.net.ssl.internal.ssl.Provider 
-security.provider.5=com.sun.crypto.provider.SunJCE 
-security.provider.6=sun.security.jgss.SunProvider 
-security.provider.7=com.sun.security.sasl.Provider
>Get Provider List 
>44
import java.security.Provider; 
import java.security.Provider.Service; 
import java.security.Security; 
public class ProviderTest { public static void main(String[] args) { 
	for (Provider p : Security.getProviders()) { 
	System.out.println("========================"); 
	System.out.println("Provider: " + p.getName()); 
	//for (Service s : p.getServices()) { 
	//System.out.println(s.getAlgorithm()); 
		} 
	} 
}



















