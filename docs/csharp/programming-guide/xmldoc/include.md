---
title: "&lt;include&gt;(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "include"
  - "<include>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<include> C# XML 태그"
  - "include C# XML 태그"
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# &lt;include&gt;(C# 프로그래밍 가이드)
## 구문  
  
```  
<include file='filename' path='tagpath[@name="id"]' />  
```  
  
#### 매개 변수  
 `filename`  
 문서를 포함할 XML 파일 이름입니다.  파일 이름은 path로 한정될 수 있습니다.  `filename`은 작은따옴표\(' '\)로 묶습니다.  
  
 `tagpath`  
 태그의 `name`을 찾을 수 있는 `filename`의 태그 경로입니다.  path는 작은따옴표\(' '\)로 묶습니다.  
  
 `name`  
 주석 앞에 오는 태그의 이름 지정자입니다. `name`에는 `id`가 있어야 합니다.  
  
 `id`  
 주석 앞에 오는 태그의 ID입니다.  ID는 큰따옴표\(" "\)로 묶습니다.  
  
## 설명  
 \<include\> 태그를 사용하면 소스 코드의 형식과 멤버를 설명하는 다른 파일의 주석을 참조할 수 있습니다.  이렇게 하면 소스 코드 파일에 직접 문서 주석을 배치하지 않아도 됩니다.  설명서를 별도의 파일에 넣어 사용자가 소스 제어에서 별도로 문서에 소스 코드를 적용할 수 있습니다.  한 사람이 소스 코드 파일을 체크 아웃할 수 있으며 다른 사람이 설명서 파일을 체크 아웃할 수 있습니다.  
  
 \<include\> 태그는 XML XPath 구문을 사용합니다.  \<include\>의 용도를 변경하는 방법은 XPath 문서를 참조하십시오.  
  
## 예제  
 아래 예제는 여러 개의 파일로 구성됩니다.  \<include\>를 사용하는 첫째 파일은 아래와 같습니다.  
  
 [!code-cs[csProgGuideDocComments#5](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/include_1.cs)]  
  
 두 번째 파일 xml\_include\_tag.doc에는 다음 문서 주석이 있습니다.  
  
```  
<MyDocs>  
  
<MyMembers name="test">  
<summary>  
The summary for this type.  
</summary>  
</MyMembers>  
  
<MyMembers name="test2">  
<summary>  
The summary for this other type.  
</summary>  
</MyMembers>  
  
</MyDocs>  
```  
  
## 프로그램 출력  
 다음 출력은 다음 명령줄을 사용하여 Test 및 Test2 클래스를 컴파일할 때 생성됩니다. `/doc:DocFileName.xml.` Visual Studio에서는 프로젝트 디자이너의 빌드 창에 XML doc 주석 옵션을 지정합니다.  C\# 컴파일러가 \<inclue\> 태그를 볼 때, 현재 소스 파일 대신 xml\_include\_tag.doc 문서 주석을 검색합니다.  그런 다음 컴파일러가 DocFileName.xml을 생성하고 이 파일은 [Sandcastle](http://go.microsoft.com/fwlink/?LinkId=124061) 같은 문서 도구에서 최종 문서를 생성하기 위해 사용되는 파일입니다.  
  
```  
<?xml version="1.0"?>   
<doc>   
    <assembly>   
        <name>xml_include_tag</name>   
    </assembly>   
    <members>   
        <member name="T:Test">   
            <summary>   
The summary for this type.   
</summary>   
        </member>   
        <member name="T:Test2">   
            <summary>   
The summary for this other type.   
</summary>   
        </member>   
    </members>   
</doc>   
```  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)