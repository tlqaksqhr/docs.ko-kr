---
title: "/bugreport (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/bugreport"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/bugreport compiler option [C#]"
  - "-bugreport compiler option [C#]"
  - "bugreport compiler option [C#]"
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /bugreport (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

나중에 분석할 수 있도록 디버그 정보를 파일에 포함하도록 지정합니다.  
  
## 구문  
  
```  
/bugreport:file  
```  
  
## 인수  
 `file`  
 버그 보고서를 포함할 파일의 이름입니다.  
  
## 설명  
 **\/bugreport** 옵션은 다음 정보를 `file`에 포함하도록 지정합니다.  
  
-   컴파일에 사용된 모든 소스 코드 파일의 복사본  
  
-   컴파일에 사용된 컴파일러 옵션 목록  
  
-   컴파일러, 런타임 및 운영 체제의 버전 정보  
  
-   참조된 어셈블리 및 모듈\(16진수로 저장\). 여기서 .NET Framework 및 SDK와 함께 제공되는 어셈블리는 제외됩니다.  
  
-   컴파일러 출력\(있는 경우\)  
  
-   화면에 표시되는 문제에 대한 설명  
  
-   화면에 표시되는 문제 해결 방법에 대한 설명  
  
 이 옵션을 **\/errorreport:prompt** 또는 **\/errorreport:send**와 함께 사용하면 파일의 정보가 Microsoft Corporation에 보내집니다.  
  
 모든 소스 코드 파일의 복사본은 `file`에 저장되기 때문에 오류 가능성이 있는 코드를 가능한 한 가장 짧은 프로그램으로 재현할 수도 있습니다.  
  
 이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수도 없습니다.  
  
 생성된 파일의 내용에서는 소스 코드를 노출하므로 의도하지 않은 정보 노출의 위험이 있습니다.  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [\/errorreport \(Set Error Reporting Behavior\)](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)