---
title: "문서 태그에 대한 구분 기호(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/** */ C# 문서 태그의 구분 기호"
  - "/// C# 문서의 구분 기호"
  - "XML[C#], 구분 기호"
ms.assetid: 9b2bdd18-4f5c-4c0b-988e-fb992e0d233e
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# 문서 태그에 대한 구분 기호(C# 프로그래밍 가이드)
XML 문서 주석을 사용하려면 문서 주석이 시작되고 끝나는 위치를 컴파일러에 알리는 구분 기호를 사용해야 합니다.  XML 문서 태그에는 다음과 같은 구분 기호를 사용할 수 있습니다.  
  
 `///`  
 한 줄 구분 기호입니다.  문서 예제에 표시되는 형식이며 Visual C\# 프로젝트 템플릿에서 사용합니다.  구분 기호 뒤에 공백 문자가 있으면 해당 문자는 XML 출력에 나타나지 않습니다.  
  
> [!NOTE]
>  Visual Studio IDE에는 코드 편집기에 `///`를 입력하면 \<summary\> 및 \<\/summary\> 태그를 자동으로 삽입하고 커서를 이 태그 내로 이동하는 주석 스마트 편집이라는 기능이 있습니다.  프로젝트 속성 페이지의 [옵션, 텍스트 편집기, C\#, 서식](/visual-studio/ide/reference/options-text-editor-csharp-formatting)에서 이 기능에 액세스할 수 있습니다.  
  
 `/** */`  
 여러 줄 구분 기호입니다.  
  
 `/** */` 구분 기호를 사용할 때는 몇 가지 서식 지정 규칙을 준수해야 합니다.  
  
-   `/**` 구분 기호가 있는 줄의 나머지 부분이 공백이면 해당 줄이 주석으로 처리되지 않습니다.  `/**` 구분 기호 뒤의 첫 번째 문자가 공백이면 공백 문자가 무시되고 줄의 나머지 부분이 처리됩니다.  그렇지 않으면 `/**` 구분 기호 뒤에 나오는 전체 텍스트가 주석의 일부로 처리됩니다.  
  
-   `*/` 구분 기호가 있는 줄에서 `*/` 구분 기호 앞이 모두 공백이면 해당 줄이 무시됩니다.  그렇지 않으면 `*/` 구분 기호 앞의 텍스트가 다음 목록에서 설명하는 패턴 일치 규칙에 따라 주석의 일부로 처리됩니다.  
  
-   컴파일러가 `/**` 구분 기호로 시작하는 줄 뒤의 각 줄의 시작 부분에서 공통 패턴이 있는지 찾습니다.  패턴은 별표\(`*`\)와 별표 앞뒤에 선택적 공백을 사용하여 구성할 수 있습니다.  컴파일러가 각 줄의 시작 부분에서 `/**` 구분 기호 또는 `*/` 구분 기호로 시작되지 않는 공통 패턴을 찾으면 각 줄의 해당 패턴을 무시합니다.  
  
 다음 예제에서는 이러한 규칙을 설명합니다.  
  
-   다음 주석에서는 `<summary>`로 시작하는 줄만 처리됩니다.  세 가지 형식의 태그는 같은 주석을 만듭니다.  
  
    ```  
    /** <summary>text</summary> */   
  
    /**   
    <summary>text</summary>   
    */   
  
    /**   
     * <summary>text</summary>   
    */  
  
    ```  
  
-   컴파일러가 두 번째 및 세 번째 줄의 시작 부분에서 일반 패턴 " \* "를 확인합니다.  패턴은 출력에 포함되지 않습니다.  
  
    ```  
    /**   
     * <summary>   
     * text </summary>*/   
    ```  
  
-   다음 주석에서 세 번째 행의 두 번째 문자가 별표가 아니므로 컴파일러가 일반 패턴을 찾지 못합니다.  따라서 두 번째 줄과 세 번째 줄의 모든 텍스트가 주석의 일부로 처리됩니다.  
  
    ```  
    /**   
     * <summary>   
       text </summary>  
    */   
    ```  
  
-   다음 주석에서는 두 가지 이유로 컴파일러가 패턴을 찾지 못합니다.  첫째, 별표 앞의 공백 수가 일치하지 않습니다.  둘째, 다섯 번째 줄이 탭으로 시작하는데, 탭은 공백과 일치하지 않습니다.  따라서 두 번째 줄부터 다섯 번째 줄까지의 모든 텍스트가 주석의 일부로 처리됩니다.  
  
    ```  
    /**   
      * <summary>   
      * text   
     *  text2   
        *  </summary>   
    */   
    ```  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [XML 문서 주석](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)   
 [\/doc \(Process Documentation Comments\)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)   
 [XML 문서 주석](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)