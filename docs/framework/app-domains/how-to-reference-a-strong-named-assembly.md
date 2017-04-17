---
title: "방법: 강력한 이름의 어셈블리 참조 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "어셈블리[.NET Framework], 강력한 이름"
  - "어셈블리 바인딩, 강력한 이름"
  - "컴파일 타임 어셈블리 참조"
  - "강력한 이름의 어셈블리, 컴파일 타임 참조"
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 강력한 이름의 어셈블리 참조
강력한 이름의 어셈블리에서 형식이나 리소스를 참조하는 프로세스는 대개 명확합니다.  참조는 컴파일 타임\(초기 바인딩\)이나 런타임에 만들 수 있습니다.  
  
 컴파일러에서 사용자 어셈블리가 다른 어셈블리를 명시적으로 참조하는 경우, 컴파일 타임 참조가 발생합니다.  컴파일 타임 참조를 사용하는 경우, 컴파일러는 대상 어셈블리의 공개 키를 가져와서 이 키를 컴파일될 어셈블리의 어셈블리 참조에 자동으로 저장합니다.  
  
> [!NOTE]
>  강력한 이름의 어셈블리는 다른 강력한 이름의 어셈블리 형식만 사용할 수 있습니다.  그렇지 않으면 강력한 이름의 어셈블리에 대한 보안이 손상됩니다.  
  
### 강력한 이름의 어셈블리를 컴파일 타임에 참조하려면  
  
1.  명령 프롬프트에 다음 명령을 입력합니다.  
  
     \<*compiler command*\> **\/reference:**\<*assembly name*\>  
  
     이 명령에서 *compiler command* 는 사용되는 언어의 컴파일러 명령이고, *assembly name* 은 참조되는 어셈블리의 강력한 이름입니다.  또한 라이브러리 어셈블리를 만들기 위한 **\/t:library** 옵션과 같은 다른 컴파일러 옵션도 사용할 수 있습니다.  
  
 다음 예제는 `myAssembly.dll`이라는 어셈블리를 만드는데, 이 어셈블리는 `myLibAssembly.dll`이라는 강력한 이름의 어셈블리를 `myAssembly.cs` 모듈에서 참조합니다.  
  
```  
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  
  
### 강력한 이름의 어셈블리를 런타임에 참조하려면  
  
1.  <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 메서드 또는 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName> 메서드를 사용하는 경우처럼 런타임에 강력한 이름의 어셈블리를 참조하려면 참조되는 강력한 이름의 어셈블리의 표시 이름을 사용해야 합니다.  표시 이름의 구문은 다음과 같습니다.  
  
     \<*assembly name*\>**,** \<*version number*\>**,** \<*culture*\>**,** \<*public key token*\>  
  
     예를 들면 다음과 같습니다.  
  
    ```  
    myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33   
    ```  
  
     이 예제에서 `PublicKeyToken`은 16진수 형태의 공개 키 토큰입니다.  문화권 값이 없으면 `Culture=neutral`을 사용합니다.  
  
 다음 코드 예제에서는 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 메서드에서 이 정보를 사용하는 방법을 보여 줍니다.  
  
 [!code-cpp[Assembly.Load1#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.Load1/CPP/load2.cpp#3)]
 [!code-csharp[Assembly.Load1#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.Load1/CS/load2.cs#3)]
 [!code-vb[Assembly.Load1#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.Load1/VB/load2.vb#3)]  
  
 다음 [강력한 이름\(Sn.exe\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) 명령을 사용하면 특정 어셈블리의 공개 키 토큰과 16진수 형태의 공개 키를 출력할 수 있습니다.  
  
 **sn \-Tp \<** *assembly* **\>**  
  
 공개 키 파일이 있는 경우는 다음 명령을 대신 사용할 수 있습니다. 명령줄 옵션의 대\/소문자에 주목합니다.  
  
 **sn \-tp \<** *assembly* **\>**  
  
## 참고 항목  
 [강력한 이름의 어셈블리 만들기 및 사용](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)