---
title: "/warnaserror (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/warnaserror"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/warnaserror compiler option [C#]"
  - "-warnaserror compiler option [C#]"
  - "warnaserror compiler option [C#]"
ms.assetid: 04680ec3-08d6-4e2e-a274-38310e10e33c
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# /warnaserror (C# Compiler Options)
**\/warnaserror\+** 옵션을 사용하면 모든 경고가 오류로 처리됩니다.  
  
## 구문  
  
```  
/warnaserror[<U>+</U> | -][:warning-list]  
```  
  
## 설명  
 일반적으로는 경고로 보고될 메시지가 경고 대신 오류로 보고되고, 빌드 프로세스는 중지되므로 출력 파일이 빌드되지 않습니다.  
  
 기본적으로는 **\/warnaserror\-**가 설정되어 있으므로 경고가 발생해도 출력 파일은 생성됩니다.  **\/warnaserror**는 **\/warnaserror\+**와 같으며 경고를 오류로 처리합니다.  
  
 필요에 따라 특정 경고만 오류로 처리하려는 경우 오류로 처리할 경고 번호를 쉼표로 구분하여 지정할 수도 있습니다.  
  
 컴파일러에서 표시할 경고 수준을 지정하려면 [\/warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md)을 사용합니다.  특정 경고를 비활성화하려면 [\/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md)을 사용합니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  
  
2.  **빌드** 속성 페이지를 클릭합니다.  
  
3.  **경고를 오류로 처리** 속성을 수정합니다.  
  
     프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors%2A>를 참조하십시오.  
  
## 예제  
 `in.cs`를 컴파일하고 컴파일러에서 경고를 표시하지 않도록 합니다.  
  
```  
csc /warnaserror in.cs  
csc /warnaserror:642,649,652 in.cs  
```  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)