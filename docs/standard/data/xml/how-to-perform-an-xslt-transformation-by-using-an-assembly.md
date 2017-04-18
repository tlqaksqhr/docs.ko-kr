---
title: "방법: 어셈블리를 사용하여 XSLT 변환 수행 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 76ee440b-d134-4f8f-8262-b917ad6dcbf6
caps.latest.revision: 2
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 2
---
# 방법: 어셈블리를 사용하여 XSLT 변환 수행
XSLT 컴파일러\(xsltc.exe\)에서는 XSLT 스타일시트를 컴파일하여 어셈블리를 생성합니다.  그런 다음 어셈블리를 <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=fullName> 메서드로 직접 전달할 수 있습니다.  
  
### XML 및 XSLT 파일을 로컬 컴퓨터에 복사하려면  
  
-   XSLT 파일을 로컬 컴퓨터에 복사하고 이름을 Transform.xsl로 지정합니다.  
  
    ```  
    <xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
      xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
      xmlns:user="urn:my-scripts">  
      <msxsl:script language="C#" implements-prefix="user">  
        <![CDATA[  
      public string discount(string price){  
        char[] trimChars = { '$' };  
        //trim leading $, convert price to type double  
        double discount_value = Convert.ToDouble(price.TrimStart(trimChars));  
        //apply 10% discount and round appropriately  
        discount_value = .9*discount_value;  
        //convert value to decimal and format as currency  
        string discount_price = discount_value.ToString("C");  
        return discount_price;  
      }  
      ]]>  
      </msxsl:script>  
      <xsl:template match="catalog">  
        <html>  
          <head></head>  
          <body>  
            <table border="1">  
              <tr>  
                <th align="left">Title</th>  
                <th align="left">Author</th>  
                <th align="left">Genre</th>  
                <th align="left">Publish Date</th>  
                <th align="left">Price</th>  
              </tr>  
              <xsl:for-each select="book">  
                <tr>  
                  <td>  
                    <xsl:value-of select="title"/>  
                  </td>  
                  <td>  
                    <xsl:value-of select="author"/>  
                  </td>  
                  <td>  
                    <xsl:value-of select="genre"/>  
                  </td>  
                  <td>  
                    <xsl:value-of select="publish_date"/>  
                  </td>  
                  <xsl:choose>  
                    <xsl:when test="genre = 'Fantasy'">  
                      <td>  
                        <xsl:value-of select="user:discount(price)"/>  
                      </td>  
                    </xsl:when>  
                    <xsl:otherwise>  
                      <td>  
                        <xsl:value-of select="price"/>  
                      </td>  
                    </xsl:otherwise>  
                  </xsl:choose>  
                </tr>  
              </xsl:for-each>  
            </table>  
          </body>  
        </html>  
      </xsl:template>  
    </xsl:stylesheet>  
    ```  
  
-   XML 파일을 로컬 컴퓨터에 복사하고 이름을 `books.xml`로 지정합니다.  
  
    ```  
    <?xml version="1.0"?>  
    <catalog>  
       <book id="bk101">  
          <author>Gambardella, Matthew</author>  
          <title>XML Developer's Guide</title>  
          <genre>Computer</genre>  
          <price>$44.95</price>  
          <publish_date>2000-10-01</publish_date>  
       </book>  
       <book id="bk102">  
          <author>Ralls, Kim</author>  
          <title>Midnight Rain</title>  
          <genre>Fantasy</genre>  
          <price>$5.95</price>  
          <publish_date>2000-12-16</publish_date>  
       </book>  
       <book id="bk103">  
          <author>Corets, Eva</author>  
          <title>Maeve Ascendant</title>  
          <genre>Fantasy</genre>  
          <price>$5.95</price>  
          <publish_date>2000-11-17</publish_date>  
       </book>  
       <book id="bk106">  
          <author>Randall, Cynthia</author>  
          <title>Lover Birds</title>  
          <genre>Romance</genre>  
          <price>$4.95</price>  
          <publish_date>2000-09-02</publish_date>  
       </book>  
       <book id="bk107">  
          <author>Thurman, Paula</author>  
          <title>Splish Splash</title>  
          <genre>Romance</genre>  
          <price>$4.95</price>  
          <publish_date>2000-11-02</publish_date>  
       </book>  
    </catalog>  
    ```  
  
### 스크립트가 활성화된 스타일시트를 컴파일하려면  
  
1.  명령줄에서 다음 명령을 실행하면 이름이 `Transform.dll` 및 `Transform_Script1.dll`인 두 개의 어셈블리가 만들어집니다.  이것이 기본 동작이며, 아무 것도 지정하지 않으면 클래스 및 어셈블리 이름은 기본 스타일시트 이름으로 지정됩니다.  
  
    ```  
    xsltc /settings:script+ Transform.xsl  
    ```  
  
 다음 명령에서는 명시적으로 클래스 이름을 Transform으로 설정합니다.  
  
```  
xsltc /settings:script+ /class:Transform Transform.xsl  
```  
  
### 코드를 컴파일할 때 컴파일된 어셈블리를 참조로 포함하려면  
  
1.  Visual Studio의 솔루션 탐색기에서 참조를 추가하거나 명령줄을 사용하여 어셈블리를 포함할 수 있습니다.  
  
2.  C\#을 사용하는 명령줄의 경우 다음을 사용합니다.  
  
    ```  
    csc myCode.cs /r:system.dll;system.xml.dll;Transform.dll  
    ```  
  
3.  Visual Basic을 사용하는 명령줄의 경우 다음을 사용합니다.  
  
    ```  
    vbc myCode.vb /r:system.dll;system.xml.dll;Transform.dll  
    ```  
  
### 사용자 코드에서 컴파일된 어셈블리를 사용하려면  
  
1.  다음 예제에서는 컴파일된 스타일시트를 사용하여 XSLT 변환을 실행하는 방법을 보여 줍니다.  
  
 [!code-csharp[XslTransform_XSLTC#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XslTransform_XSLTC/CS/XslTransform_XSLTC.cs#1)]
 [!code-vb[XslTransform_XSLTC#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslTransform_XSLTC/VB/XslTransform_XSLTC.vb#1)]  
  
 위 예제에서 컴파일된 어셈블리에 동적으로 연결하려면  
  
```  
xslt.Load(typeof(Transform))  
```  
  
 다음으로 바꾸면 됩니다.  
  
```  
xslt.Load(System.Reflection.Assembly.Load("Transform").GetType("Transform"))  
```  
  
 으로 대체합니다.  Assembly.Load 메서드에 대한 자세한 내용은 <xref:System.Reflection.Assembly.Load%2A>를 참조하세요.  
  
## 참고 항목  
 <xref:System.Xml.Xsl.XslCompiledTransform>   
 [XSLT 컴파일러\(xsltc.exe\)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)   
 [XSLT 변환](../../../../docs/standard/data/xml/xslt-transformations.md)   
 [csc.exe를 사용한 명령줄 빌드](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)