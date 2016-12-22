---
title: "/keycontainer (C# Compiler Options) | Microsoft Docs"
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
  - "/keycontainer"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/keycontainer compiler option [C#]"
  - "keycontainer compiler option [C#]"
  - "-keycontainer compiler option [C#]"
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /keycontainer (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

암호화 키 컨테이너의 이름을 지정합니다.  
  
## 구문  
  
```  
/keycontainer:string  
```  
  
## 인수  
 `string`  
 강력한 이름 키 컨테이너의 이름입니다.  
  
## 설명  
 **\/keycontainer** 옵션을 사용하면 컴파일러는 지정된 컨테이너의 공개 키를 어셈블리 매니페스트에 삽입하고 개인 키를 사용하여 최종 어셈블리에 서명하는 방식으로 공유 가능한 구성 요소를 만듭니다.  키 파일을 생성 하기 위해, sn\-k `file` 을 명령줄에서 입력하십이오. sn\-i는 컨테이너에 키 쌍을 설치 합니다.  
  
 [\/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)을 사용하여 컴파일하면 키 파일의 이름이 해당 모듈에 저장되고 [\/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md)을 사용하여 모듈이 어셈블리로 컴파일될 경우 만들어지는 최종 어셈블리에서 이 정보를 사용할 수 있습니다.  
  
 MSIL\(Microsoft Intermediate Language\) 모듈의 소스 코드에서 이 옵션을 사용자 지정 특성\(<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName>\)으로 지정할 수도 있습니다.  
  
 [\/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)을 사용하여 컴파일러에 암호화 정보를 전달할 수도 있습니다.  어셈블리 매니페스트에 공개 키를 추가할 계획이지만 테스트가 완료될 때까지 어셈블리 서명을 연기하려면 [\/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md)을 사용하십시오.  
  
 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md) 및 [어셈블리 서명 연기](../Topic/Delay%20Signing%20an%20Assembly.md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  이 컴파일러 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다.  
  
 <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>을 사용하여 프로그래밍 방식으로 이 컴파일러 옵션에 액세스할 수 있습니다.  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)