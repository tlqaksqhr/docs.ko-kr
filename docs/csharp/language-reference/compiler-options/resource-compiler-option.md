---
title: "/resource (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/resource"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-resource compiler option [C#]"
  - "/resource compiler option [C#]"
  - "-res compiler option [C#]"
  - "/res compiler option [C#]"
  - "res compiler option [C#]"
  - "resource compiler option [C#]"
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# /resource (C# Compiler Options)
출력 파일에 지정된 리소스를 포함시킵니다.  
  
## 구문  
  
```  
/resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## 인수  
 `filename`  
 출력 파일에 포함시킬 .NET Framework 리소스 파일입니다.  
  
 `identifier`\(선택적 요소\)  
 리소스의 논리적 이름, 즉 리소스를 로드하는 데 사용되는 이름입니다.  기본값은 파일 이름입니다.  
  
 `accessibility-modifier`\(선택적 요소\)  
 리소스의 액세스 가능성이며, public 또는 private으로 지정됩니다.  기본값은 public입니다.  
  
## 설명  
 [\/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md)를 사용하면 리소스를 어셈블리에 링크하고 출력 파일에는 리소스 파일을 추가하지 않습니다.  
  
 기본적으로 C\# 컴파일러를 사용하여 리소스를 만들면 해당 리소스는 어셈블리에서 public입니다.  리소스를 private으로 만들려면 액세스 가능성 한정자로 `private`을 지정합니다.  `public` 또는 `private` 액세스 가능성만 사용할 수 있습니다.  
  
 `filename`이 [Resgen.exe](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md)를 사용하여 만들었거나 개발 환경에서 만든 .NET Framework 리소스 파일인 경우 이 파일은 <xref:System.Resources> 네임스페이스의 멤버를 사용하여 액세스할 수 있습니다.  자세한 내용은 <xref:System.Resources.ResourceManager?displayProperty=fullName>을 참조하십시오.  다른 모든 리소스의 경우 런타임에 <xref:System.Reflection.Assembly> 클래스의 `GetManifestResource`\* 메서드를 사용하여 리소스에 액세스합니다.  
  
 **\/res**는 **\/resource**의 약식 표현입니다.  
  
 출력 파일에서 리소스의 순서는 명령줄에 지정된 순서에 따라 결정됩니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트에 리소스 파일을 추가합니다.  
  
2.  **솔루션 탐색기**에서 포함시킬 파일을 선택합니다.  
  
3.  **속성** 창에서 파일에 대한 **빌드 작업**을 선택합니다.  
  
4.  **빌드 작업**을 **포함 리소스**로 설정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.FileProperties2.BuildAction%2A>을 참조하십시오.  
  
## 예제  
 `in.cs`를 컴파일하고 리소스 파일 `rf.resource`를 추가합니다.  
  
```  
csc /resource:rf.resource in.cs  
```  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)