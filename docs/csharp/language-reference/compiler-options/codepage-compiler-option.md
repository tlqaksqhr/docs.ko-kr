---
title: "/codepage (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/codepage"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/codepage compiler option [C#]"
  - "codepage compiler option [C#]"
  - "-codepage compiler option [C#]"
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# /codepage (C# Compiler Options)
이 옵션은 필요한 페이지가 시스템의 현재 기본 코드 페이지가 아닌 경우 컴파일하는 동안 사용할 코드 페이지를 지정하는 데 사용됩니다.  
  
## 구문  
  
```  
/codepage:id  
```  
  
## 인수  
 `id`  
 컴파일할 때 모든 소스 코드 파일에 사용할 코드 페이지의 ID입니다.  
  
## 설명  
 컴퓨터에서 기본 코드 페이지를 사용하도록 만들어지지 않은 하나 이상의 소스 코드 파일을 컴파일하는 경우 **\/codepage** 옵션을 사용하면 사용할 코드 페이지를 지정할 수 있습니다.  **\/codepage**는 컴파일에 사용되는 모든 소스 코드 파일에 적용됩니다.  
  
 소스 코드 파일이 컴퓨터에 적용된 것과 동일한 코드 페이지로 만들어졌거나 소스 코드 파일이 유니코드 또는 UTF\-8로 만들어졌으면 **\/codepage**를 사용할 필요가 없습니다.  
  
 시스템에서 지원되는 코드 페이지에 대한 자세한 내용은 다음을 참조하십시오. [GetCPInfo](http://go.microsoft.com/fwlink/?LinkId=148371)  
  
 이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수도 없습니다.  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)