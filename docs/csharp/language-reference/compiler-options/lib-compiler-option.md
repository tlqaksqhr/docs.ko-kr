---
title: "/lib (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/lib"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lib compiler option [C#]"
  - "-lib compiler option [C#]"
  - "/lib compiler option [C#]"
ms.assetid: b0efcc88-e8aa-4df4-a00b-8bdef70b7673
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /lib (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

**\/lib** 옵션은 [\/reference \(Import Metadata\)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) 옵션을 통해 참조되는 어셈블리의 위치를 지정합니다.  
  
## 구문  
  
```  
/lib:dir1[,dir2]  
```  
  
## 인수  
 `dir1`  
 참조된 어셈블리가 현재 작업 디렉터리\(컴파일러를 실행하는 디렉터리\)나 공용 언어 런타임의 시스템 디렉터리에 없을 경우 컴파일러가 찾는 디렉터리입니다.  
  
 `dir2`  
 어셈블리 참조를 검색하는 하나 이상의 추가 디렉터리입니다.  추가 디렉터리 이름은 쉼표로 구분하며 각 디렉터리 이름 사이에 공백을 두지 않습니다.  
  
## 설명  
 컴파일러에서는 정규화된 경로에 없는 어셈블리 참조를 다음 순서에 따라 검색합니다.  
  
1.  현재 작업 디렉터리.  컴파일러를 실행한 디렉터리입니다.  
  
2.  공용 언어 런타임 시스템 디렉터리  
  
3.  **\/lib**에서 지정한 디렉터리  
  
4.  LIB 환경 변수에서 지정한 디렉터리  
  
 어셈블리 참조를 지정하려면 **\/reference**를 사용합니다.  
  
 **\/lib**는 계속 추가할 수 있는 옵션이며, 이 옵션을 두 번 이상 지정하면 이전 값에 추가됩니다.  
  
 **\/lib**를 사용하는 대신 필요한 어셈블리를 작업 디렉터리에 복사할 수 있습니다. 이렇게 하면 **\/reference**에 어셈블리 이름을 쉽게 전달할 수 있습니다.  그런 다음 작업 디렉터리에서 해당 어셈블리를 삭제할 수 있습니다.  종속 어셈블리의 경로가 어셈블리 매니페스트에 지정되지 않았기 때문에 응용 프로그램은 대상 컴퓨터에서 시작될 수 있으며 전역 어셈블리 캐시에서 어셈블리를 찾아 사용합니다.  
  
 컴파일러가 어셈블리를 참조할 수 있다고 해서 공용 언어 런타임에서 런타임에 어셈블리를 찾아 로드할 수 있는 것은 아닙니다.  런타임에서 참조된 어셈블리를 검색하는 방법에 대한 자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../Topic/How%20the%20Runtime%20Locates%20Assemblies.md)을 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  
  
2.  **참조 경로** 속성 페이지를 클릭합니다.  
  
3.  목록 상자의 내용을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법은 <xref:VSLangProj80.ProjectProperties3.ReferencePath%2A>를 참조하십시오.  
  
## 예제  
 t2.cs를 컴파일하여 .exe 파일을 만듭니다.  컴파일러는 작업 디렉터리와 C 드라이브의 루트 디렉터리에서 어셈블리 참조를 찾습니다.  
  
```  
csc /lib:c:\ /reference:t2.dll t2.cs  
```  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)