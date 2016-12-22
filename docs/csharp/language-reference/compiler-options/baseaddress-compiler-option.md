---
title: "/baseaddress (C# Compiler Options) | Microsoft Docs"
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
  - "/dllbase"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "baseaddress compiler option [C#]"
  - "/baseaddress compiler option [C#]"
  - "-baseaddress compiler option [C#]"
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /baseaddress (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

**\/baseaddress** 옵션으로 DLL을 로드할 기본 설정 기준 주소를 지정할 수 있습니다.  이 옵션을 사용 하는 이유 및 시기에 대한 자세한 내용은, [응용 프로그램 시작 시간 개선](http://go.microsoft.com/fwlink/?LinkId=107043) 및 [Larry Osterman의 웹 블로그](http://go.microsoft.com/fwlink/?LinkId=107044) 를 참조하십시오.  
  
## 구문  
  
```  
/baseaddress:address  
```  
  
## 인수  
 `address`  
 DLL의 기준 주소입니다.  이 주소는 10진수, 16진수 또는 8진수로 지정할 수 있습니다.  
  
## 설명  
 DLL의 기본 기준 주소는 .NET Framework 공용 언어 런타임에 의해 설정됩니다.  
  
 이 주소의 하위 단어는 반올림됩니다.  예를 들어, 0x11110001을 지정할 경우 0x11110000으로 반올림됩니다.  
  
 DLL의 서명 프로세스를 완료하려면 SN.EXE를 \-R 옵션과 함께 사용합니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  
  
2.  **빌드** 속성 페이지를 클릭합니다.  
  
3.  **고급** 단추를 클릭합니다.  
  
4.  **DLL 기준 주소** 속성을 수정합니다.  
  
     프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=fullName>   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)