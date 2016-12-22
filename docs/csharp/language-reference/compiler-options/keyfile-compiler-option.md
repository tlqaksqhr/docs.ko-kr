---
title: "/keyfile (C# Compiler Options) | Microsoft Docs"
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
  - "/keyfile"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/keyfile compiler option [C#]"
  - "-keyfile compiler option [C#]"
  - "keyfile compiler option [C#]"
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /keyfile (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

암호화 키를 포함하는 파일 이름을 지정합니다.  
  
## 구문  
  
```  
/keyfile:file  
```  
  
## 인수  
  
|용어|정의|  
|--------|--------|  
|`file`|강력한 이름 키를 포함하는 파일의 이름입니다.|  
  
## 설명  
 이 옵션을 사용하면 컴파일러에서는 지정된 파일의 공개 키를 어셈블리 매니페스트에 삽입한 다음 개인 키를 사용하여 최종 어셈블리에 서명합니다.  키 파일을 생성하려면 명령줄에 sn \-k `file`을 입력하십시오.  
  
 **\/target:module**을 사용하여 컴파일하면 키 파일의 이름이 해당 모듈에 저장되고 [\/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md)을 사용하여 어셈블리를 컴파일할 때 만들어지는 어셈블리에서 이 정보를 사용할 수 있습니다.  
  
 [\/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md)를 사용하여 컴파일러에 암호화 정보를 전달할 수도 있습니다.  부분적으로 서명된 어셈블리를 원하면 [\/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md)을 사용하십시오.  
  
 명령줄 옵션 또는 사용자 지정 특성을 통해 동일한 컴파일에 \/keyfile과 \/keycontainer가 모두 지정된 경우 컴파일러에서는 키 컨테이너를 먼저 시도합니다.  키 컨테이너에서 성공하면 어셈블리는 키 컨테이너의 정보로 서명됩니다.  키 컨테이너를 찾지 못할 경우 컴파일러에서는 \/keyfile로 지정된 파일을 시도합니다.  키 파일에서 성공하면 어셈블리는 키 파일의 정보로 서명되며 다음에 컴파일할 때 키 컨테이너를 사용할 수 있도록 키 정보가 키 컨테이너에 설치됩니다\(sn \-i와 유사\).  
  
 키 파일에는 공개 키만 포함될 수 있습니다.  
  
 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md) 및 [어셈블리 서명 연기](../Topic/Delay%20Signing%20an%20Assembly.md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  
  
2.  **서명** 속성 페이지를 클릭합니다.  
  
3.  **강력한 이름 키 파일 선택** 속성을 수정합니다.  
  
 <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>을 사용하여 프로그래밍 방식으로 이 컴파일러 옵션에 액세스할 수 있습니다.  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)