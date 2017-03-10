---
title: "/linkresource (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/linkresource"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/linkresource compiler option [C#]"
  - "linkres compiler option [C#]"
  - "/linkres compiler option [C#]"
  - "-linkres compiler option [C#]"
  - "-linkresource compiler option [C#]"
  - "linkresource compiler option [C#]"
ms.assetid: 440c26c2-77c1-4811-a0a3-57cce3f5fc96
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# /linkresource (C# Compiler Options)
출력 파일에 .NET Framework 리소스에 대한 링크를 만듭니다.  리소스 파일은 출력 파일에 추가되지 않습니다.  이 옵션은 출력 파일에 리소스 파일을 포함시키는 [\/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) 옵션과 다릅니다.  
  
## 구문  
  
```  
/linkresource:filename[,identifier[,accessibility-modifier]]  
```  
  
## 인수  
 `filename`  
 어셈블리에서 링크할 .NET Framework 리소스 파일입니다.  
  
 `identifier`\(선택적 요소\)  
 리소스의 논리적 이름, 즉 리소스를 로드하는 데 사용되는 이름입니다.  기본값은 파일 이름입니다.  
  
 `accessibility-modifier`\(선택적 요소\)  
 리소스의 액세스 가능성이며, public 또는 private으로 지정됩니다.  기본값은 public입니다.  
  
## 설명  
 기본적으로 C\# 컴파일러를 사용하여 링크된 리소스를 만들면 해당 리소스는 어셈블리에서 public입니다.  리소스를 private으로 만들려면 액세스 가능성 한정자로 `private`을 지정합니다.  `public` 또는 `private` 한정자만 사용할 수 있습니다.  
  
 **\/linkresource**에는 **\/target:module** 대신 [\/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) 옵션 중의 하나가 필요합니다.  
  
 `filename`이 [Resgen.exe](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md)를 사용하여 만들었거나 개발 환경에서 만든 .NET Framework 리소스 파일인 경우 이 파일은 <xref:System.Resources> 네임스페이스의 멤버를 사용하여 액세스할 수 있습니다.  자세한 내용은 <xref:System.Resources.ResourceManager?displayProperty=fullName>을 참조하십시오.  다른 모든 리소스의 경우 런타임에 <xref:System.Reflection.Assembly> 클래스의 `GetManifestResource`\* 메서드를 사용하여 리소스에 액세스합니다.  
  
 `filename`에는 모든 형식의 파일을 지정할 수 있습니다.  예를 들어, 어셈블리의 네이티브 dll 부분을 전역 어셈블리 캐시에 설치하고 어셈블리의 관리 코드에서 액세스할 수 있도록 만들 수 있습니다.  다음의 두 번째 예제에서는 이러한 방법을 보여 줍니다.  어셈블리 링커에서도 동일한 작업을 수행할 수 있습니다.  다음의 세 번째 예제에서는 이러한 방법을 보여 줍니다.  자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md) 및 [어셈블리 및 전역 어셈블리 캐시 사용](../Topic/Working%20with%20Assemblies%20and%20the%20Global%20Assembly%20Cache.md)를 참조하십시오.  
  
 **\/linkres**는 **\/linkresource**의 약식 표현입니다.  
  
 이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수도 없습니다.  
  
## 예제  
 `in.cs`를 컴파일하고 리소스 파일 `rf.resource`에 링크합니다.  
  
```  
csc /linkresource:rf.resource in.cs  
```  
  
## 예제  
 `A.cs`를 DLL로 컴파일하고 네이티브 DLL N.dll에 링크한 다음 GAC\(전역 어셈블리 캐시\)에 출력 내용을 포함시킵니다.  이 예제에서는 A.dll 및 N.dll이 모두 GAC에 상주합니다.  
  
```  
csc /linkresource:N.dll /t:library A.cs  
gacutil -i A.dll  
```  
  
## 예제  
 이 예제에서는 어셈블리 링커 옵션을 사용하여 이전 예제와 동일한 작업을 수행합니다.  
  
```  
csc /t:module A.cs  
al /out:A.dll A.netmodule /link:N.dll   
gacutil -i A.dll  
```  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)   
 [어셈블리 및 전역 어셈블리 캐시 사용](../Topic/Working%20with%20Assemblies%20and%20the%20Global%20Assembly%20Cache.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)