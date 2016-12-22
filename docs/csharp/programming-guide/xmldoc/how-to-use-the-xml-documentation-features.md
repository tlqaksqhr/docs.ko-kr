---
title: "방법: XML 문서 기능 사용(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "XML 문서[C#]"
  - "C# 언어에서 XML 문서 기능"
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 방법: XML 문서 기능 사용(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

다음 샘플에 나와 있는 형식의 기본 개요를 제공 합니다.  
  
## <a name="example"></a>예제  
 [!code-cs[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]  
  
 **이.xml 파일 앞의 코드 예제를 사용 하 여 생성 되었습니다.**  
**\<? xml 버전 = "1.0"?>**  
**\< 문서>**  
 **\< 어셈블리>**  
 **\< 이름>xmlsample \< / 이름>**  
 **\< / 어셈블리>**  
 **\< 멤버>**  
 **\< 멤버 이름 = "T:SomeClass">**  
 **\< 요약>**  
 **클래스 수준 요약 설명서가 여기 있습니다. \< / 요약>**  
 **\< 설명>**  
 **더 긴 설명 형식 또는 멤버와 연결 될 수 있습니다.**   
 **설명 태그를 통해 \< remarks />**  
 **\< / 멤버>**  
 **\< 멤버 name="F:SomeClass.m_Name">**  
 **\< 요약>**  
 **Name 속성에 대 한 저장소 \< / 요약>**  
 **\< / 멤버>**  
 **\< 멤버 이름 = "M:SomeClass. #ctor">**  
 **\< 요약>클래스 생성자. \< / 요약>**   
 **\< / 멤버>**  
 **\< 멤버 name="M:SomeClass.SomeMethod(System.String)">**  
 **\< 요약>**  
 **SomeMethod.에 대 한 설명 \< / 요약>**  
 **\< m name = "s"> s에 대 한 매개 변수 설명에는 여기 \< / 매개 변수>**  
 **\< seealso cref="T:System.String">**  
 **형식 또는 멤버를 참조 하도록 모든 태그에서 cref 특성을 사용할 수 있습니다.**   
 **및 컴파일러는 참조가 있는지 확인 합니다. \< / seealso>**  
 **\< / 멤버>**  
 **\< 멤버 name="M:SomeClass.SomeOtherMethod">**  
 **\< 요약>**  
 **다른 방법입니다. \< / 요약>**  
 **\< 반환>**  
 **반환 결과 통해 반환 태그 설명 \< / 반환>**  
 **\< seealso cref="M:SomeClass.SomeMethod(System.String)">**  
 **특정 메서드를 참조 하려면 cref 특성을 사용 \< / seealso>**  
 **\< / 멤버>**  
 **\< 멤버 name="M:SomeClass.Main(System.String[])">**  
 **\< 요약>**  
 **응용 프로그램에 대 한 진입점입니다.**  
 **\< / 요약>**  
 **\< m name = "args"> 명령줄 인수 목록 \< / 매개 변수>**  
 **\< / 멤버>**  
 **\< 멤버 name="P:SomeClass.Name">**  
 **\< 요약>**  
 **Name 속성 \< / 요약>**  
 **\< 값>**  
 **속성 값을 설명 하는 값 태그 사용 \< / v>**  
 **\< / 멤버>**  
 **\< / 멤버>**  
**\< / doc>**   
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제를 컴파일하려면 다음 명령줄을 입력 합니다.  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 이 XML 파일 브라우저 또는 TYPE 명령을 사용 하 여 볼 수 있는 XMLsample.xml 만들어집니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 XML 문서는 / / /로 시작합니다. 새 프로젝트를 만들 때 마법사에서 몇 가지 시작 / / / 줄을을 넣습니다. 이러한 주석 처리에 몇 가지 제한이 있습니다.  
  
-   설명서는 제대로 구성 되어야 합니다. XML입니다. XML이 제대로 구성 된 경우에 경고가 생성 되 고 문서 파일에는 오류가 발생 했습니다 표시 하는 주석이 포함 됩니다.  
  
-   개발자는 각자의 태그를 만들 수 있습니다. 권장된 태그 (추가 정보 섹션 참조) 집합이 있습니다. 권장된 태그 중 일부는 특별 한 의미를 갖습니다.  
  
    -   \< param> 태그 매개 변수를 설명 하는 데 사용 됩니다. 사용 하는 경우 컴파일러는 매개 변수 있고 모든 매개 변수는 설명서에 설명 되어 있는지 확인 하십시오. 확인이 실패 하는 경우 컴파일러 경고를 생성 합니다.  
  
    -    `cref` 코드 요소에 대 한 참조를 제공 하기 위해 모든 태그에 특성을 연결할 수 있습니다. 컴파일러가이 코드 요소가 존재 하는지 확인 합니다. 확인이 실패 하는 경우 컴파일러 경고를 생성 합니다. 컴파일러에서는 모든 `using` 에 설명 된 형식의 찾을 때 문을 `cref` 특성입니다.  
  
    -   \< 요약> 태그 IntelliSense 사용 하 여 Visual Studio 내 형식 또는 멤버에 대 한 추가 정보를 표시 합니다.  
  
        > [!NOTE]
        >  XML 파일 형식 및 멤버에 대 한 전체 정보를 제공 하지 않습니다 (예를 들어이 포함 되지 않은 모든 형식 정보). 형식 또는 멤버에 대 한 전체 정보를 얻으려면 실제 형식이 나 멤버에 반영한 설명서 파일을 사용 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [/doc (C# 컴파일러 옵션)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)   
 [XML 문서 주석](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)