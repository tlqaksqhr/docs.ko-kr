---
title: "/delaysign (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/delaysign"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-delaysign compiler option [C#]"
  - "delaysign compiler option [C#]"
  - "/delaysign compiler option [C#]"
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# /delaysign (C# Compiler Options)
이 옵션을 사용하면 컴파일러에서는 나중에 디지털 서명을 추가할 수 있도록 출력 파일의 공간을 예약합니다.  
  
## 구문  
  
```  
/delaysign[ + | - ]  
```  
  
## 인수  
 `+` &#124; `-`  
 어셈블리에 완전히 서명하려면 **\/delaysign\-**를 사용하고  어셈블리에 공개 키만 포함하려면 **\/delaysign\+**를 사용합니다.  기본값은 **\/delaysign\-**입니다.  
  
## 설명  
 **\/delaysign** 옵션은 [\/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) 또는 [\/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md)와 함께 사용할 때에만 효과가 있습니다.  
  
 완전히 서명된 어셈블리를 요청하면 컴파일러가 매니페스트\(어셈블리 메타데이터\)가 포함된 파일을 해시한 후 해당 해시를 개인 키로 서명합니다.  결과로 생성되는 디지털 서명은 매니페스트가 포함된 파일에 저장됩니다.  어셈블리 서명이 연기되면 컴파일러가 서명을 계산하거나 저장하지 않습니다. 그러나 나중에 서명을 추가할 수 있도록 파일에 공간을 예약합니다.  
  
 예를 들어 **\/delaysign\+**를 사용하면 테스터가 어셈블리를 전역 캐시에 넣을 수 있습니다.  테스트 후에는 [어셈블리 링커](../Topic/Al.exe%20\(Assembly%20Linker\).md) 유틸리티를 통해 어셈블리에 개인 키를 입력하여 어셈블리에 완전히 서명할 수 있습니다.  
  
 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md) 및 [어셈블리 서명 연기](../Topic/Delay%20Signing%20an%20Assembly.md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  
  
2.  **서명만 연기** 속성을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법은 <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>을 참조하십시오.  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)