# Liferay and POI Integration with Maven
## A brief snippet to integrate Liferay and POI with Maven in 7.4

### POM.XML
```
<dependency>
            <groupId>org.apache.commons</groupId>
            <artifactId>commons-collections4</artifactId>
            <version>4.1</version>
            <scope>provided</scope>
        </dependency>
        <dependency>
            <groupId>org.apache.commons</groupId>
            <artifactId>commons-lang3</artifactId>
            <version>3.4</version>
            <scope>provided</scope>
        </dependency>
        <dependency>
            <groupId>org.apache.poi</groupId>
            <artifactId>poi</artifactId>
            <version>3.17</version>
            <scope>provided</scope>
        </dependency>
        <dependency>
            <groupId>org.apache.poi</groupId>
            <artifactId>poi-excelant</artifactId>
            <version>3.17</version>
            <scope>provided</scope>
        </dependency>
        <dependency>
            <groupId>org.apache.poi</groupId>
            <artifactId>poi-ooxml</artifactId>
            <version>3.17</version>
            <scope>provided</scope>
        </dependency>
        <dependency>
            <groupId>org.apache.poi</groupId>
            <artifactId>poi-ooxml-schemas</artifactId>
            <version>3.17</version>
            <scope>provided</scope>
        </dependency>
        <dependency>
            <groupId>org.apache.poi</groupId>
            <artifactId>poi-scratchpad</artifactId>
            <version>3.17</version>
            <scope>provided</scope>
        </dependency>
        <dependency>
            <groupId>org.apache.poi</groupId>
            <artifactId>ooxml-schemas</artifactId>
            <version>1.3</version>
            <scope>provided</scope>
        </dependency>
        <dependency>
            <groupId>org.apache.poi</groupId>
            <artifactId>ooxml-security</artifactId>
            <version>1.1</version>
            <scope>provided</scope>
        </dependency>
        <dependency>
            <groupId>org.apache.xmlbeans</groupId>
            <artifactId>xmlbeans</artifactId>
            <version>2.6.0</version>
            <scope>provided</scope>
        </dependency>

```

### build.gradle
```
compile group: 'org.apache.commons', name: 'commons-collections4', version: '4.1'
	compile group: 'org.apache.commons', name: 'commons-lang3', version: '3.4'
	compile group: 'org.apache.poi', name: 'poi', version: '3.17'
	compile group: 'org.apache.poi', name: 'poi-excelant', version: '3.17'
	compile group: 'org.apache.poi', name: 'poi-ooxml', version: '3.17'
	compile group: 'org.apache.poi', name: 'poi-ooxml-schemas', version: '3.17'
	compile group: 'org.apache.poi', name: 'poi-scratchpad', version: '3.17'
	compile group: 'org.apache.poi', name: 'ooxml-schemas', version: '1.3'
	compile group: 'org.apache.poi', name: 'ooxml-security', version: '1.1'
	compile group: 'org.apache.xmlbeans', name: 'xmlbeans', version: '2.6.0'
```


### bnd.bnd
```
Include-Resource:\
    @commons-collections4-4.1.jar,\
    @commons-lang3-3.4.jar,\
    @ooxml-schemas-1.3.jar,\
    @ooxml-security-1.1.jar,\
    @poi-3.17.jar,\
    @poi-ooxml-3.17.jar,\
    @poi-ooxml-schemas-3.17.jar,\
    @poi-excelant-3.17.jar,\
    @poi-scratchpad-3.17.jar,\
    @xmlbeans-2.6.0.jar

Private-Package: \
    org.apache.poi.*\

Import-Package: \
    !org.apache.poi.*,\
    !org.openxmlformats.schemas.*,\
    !schemasMicrosoftComOfficeExcel,\
    !schemasMicrosoftComOfficeOffice,\
    !schemasMicrosoftComVml,\
    !com.graphbuilder.*,\
    !com.microsoft.schemas.*,\
    !junit.framework,\
    !org.apache.jcp.xml.dsig.internal.*,\
    !org.apache.xmlbeans.*,\
    !org.bouncycastle.asn1.*,\
    !org.bouncycastle.*,\
    !org.etsi.uri.*,\
    !org.junit.*,\
    !org.w3.x2000.*,\
    !org.apache.commons.codec.digest.*,\
    !org.apache.commons.collections4.*,\
    *;resolution:=optional

```