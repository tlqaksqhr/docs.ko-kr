---
title: "/checked (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/checked"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "checked compiler option [C#]"
  - "-checked compiler option [C#]"
  - "/checked compiler option [C#]"
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# /checked (C# Compiler Options)
**\/checked** 옵션을 사용하면 결과가 데이터 형식 범위 밖의 값이 되고 [checked](../../../csharp/language-reference/keywords/checked.md) 또는 [unchecked](../../../csharp/language-reference/keywords/unchecked.md) 키워드 범위에 없는 정수 연산문에서 런타임 예외를 발생시킬지 여부를 지정할 수 있습니다.  
  
## 구문  
  
```  
/checked[+ | -]  
```  
  
## 설명  
 `checked` 또는 `unchecked` 키워드 범위에 있는 정수 연산문은 **\/checked** 옵션에 영향을 받지 않습니다.  
  
 `checked` 또는 `unchecked` 키워드 범위에 있지 않는 정수 연산문이 데이터 형식 범위 밖의 결과 값을 반환하는 경우 컴파일할 때 **\/checked\+**\(**\/checked**\)를 사용하면 해당 문은 런타임에 예외를 발생시킵니다.  **\/checked\-**가 컴파일에 사용되면 해당 문은 런타임에 예외를 발생시키지 않습니다.  
  
 이 옵션의 기본값은 **\/checked\-**입니다.  **\/checked\-**를 사용하는 시나리오 중 하나는 대규모 응용 프로그램을 빌드하는 경우입니다.  그러한 응용 프로그램을 빌드하는 데 자동화된 도구를 사용하며 그러한 도구는 **\/checked**를 \+로 자동으로 설정할 수 있습니다.  **\/checked\-**를 지정하여 도구의 전역 기본값을 재정의할 수 있습니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  자세한 내용은 [프로젝트 디자이너, 빌드 페이지\(C\#\)](/visual-studio/ide/reference/build-page-project-designer-csharp)을 참조하십시오.  
  
2.  **빌드** 속성 페이지를 클릭합니다.  
  
3.  **고급** 단추를 클릭합니다.  
  
4.  **산술 연산 오버플로\/언더플로 확인** 속성을 수정합니다.  
  
 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>를 참조하십시오.  
  
## 예제  
 다음 명령은 `t2.cs`를 컴파일합니다.  명령에서 `/checked` 옵션을 사용하면 파일의 모든 정수 연산문이 `checked` 또는 `unchecked` 키워드 범위 내에 속하지 않으며 그 결과 값은 데이터 형식 범위를 벗어나고 런타임 시 예외가 발생하도록 지정됩니다.  
  
```  
csc t2.cs /checked  
```  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)