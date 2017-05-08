---
title: "방법: 단일 파일 어셈블리 만들기 | Microsoft Docs"
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
  - "어셈블리[.NET Framework], 단일 파일"
  - "어셈블리 매니페스트, 단일 파일 어셈블리"
  - "코드 모듈"
  - "명령줄 컴파일러"
  - "라이브러리 어셈블리"
  - "어셈블리의 출력 파일 이름"
  - "단일 파일 어셈블리"
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 단일 파일 어셈블리 만들기
가장 단순한 형식의 어셈블리인 단일 파일 어셈블리에는 [어셈블리 매니페스트](../../../docs/framework/app-domains/assembly-manifest.md)뿐만 아니라 형식 정보와 구현이 들어있습니다.  단일 파일 어셈블리는 명령줄 컴파일러나 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]를 사용하여 만들 수 있습니다.  기본적으로 컴파일러는 확장명이 .exe인 어셈블리 파일을 만듭니다.  
  
> [!NOTE]
>  C\# 및 Visual Basic용 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]는 단일 파일 어셈블리를 만드는 경우에만 사용할 수 있습니다.  다중 파일 어셈블리를 만들려면 명령줄 컴파일러나 Visual C\+\+의 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]를 사용해야 합니다.  
  
 다음은 명령줄 컴파일러를 사용하여 단일 파일 어셈블리를 만드는 과정을 나타냅니다.  
  
### 확장명이 .exe인 어셈블리를 만들려면  
  
1.  명령 프롬프트에 다음 명령을 입력합니다.  
  
     \<*compiler command*\> \<*module name*\>  
  
     이 명령에서 *compiler command*는 코드 모듈에서 사용되는 언어의 컴파일러 명령이고, *module name*은 어셈블리로 컴파일할 코드 모듈의 이름입니다.  
  
 다음 예제는 `myCode`라는 코드 모듈에서 `myCode.exe`라는 어셈블리를 만듭니다.  
  
```csharp  
csc myCode.cs  
```  
  
```vb  
vbc myCode.vb  
```  
  
#### .exe 확장자로 어셈블리를 만들고 출력 파일 이름을 지정하려면  
  
1.  명령 프롬프트에 다음 명령을 입력합니다.  
  
     \<*compiler command*\> **\/out:**\<*file name*\> \<*module name*\>  
  
     이 명령에서 *compiler command*는 코드 모듈에서 사용되는 언어의 컴파일러 명령이고, *file name*은 출력 파일 이름이고, *module name*은 어셈블리로 컴파일할 코드 모듈의 이름입니다.  
  
 다음 예제는 `myCode`라는 코드 모듈에서 `myAssembly.exe`라는 어셈블리를 만듭니다.  
  
```csharp  
csc /out:myAssembly.exe myCode.cs  
```  
  
```vb  
vbc /out:myAssembly.exe myCode.vb  
```  
  
## 라이브러리 어셈블리 만들기  
 라이브러리 어셈블리는 클래스 라이브러리와 비슷합니다.  라이브러리 어셈블리에는 다른 어셈블리에서 참조되는 형식이 들어 있지만, 실행을 시작하는 진입점이 없습니다.  
  
#### 라이브러리 어셈블리를 만들려면  
  
1.  명령 프롬프트에 다음 명령을 입력합니다.  
  
     \<*compiler command*\> **\/t:library** \<*module name*\>  
  
     이 명령에서 *compiler command*는 코드 모듈에서 사용되는 언어의 컴파일러 명령이고, *module name*은 어셈블리로 컴파일할 코드 모듈의 이름입니다.  또한 **\/out:** 옵션 등의 다른 컴파일러 옵션도 사용할 수 있습니다.  
  
 다음 예제는 `myCode`라는 코드 모듈에서 `myCodeAssembly.dll`라는 라이브러리 어셈블리를 만듭니다.  
  
```csharp  
csc /out:myCodeLibrary.dll /t:library myCode.cs  
```  
  
```vb  
vbc /out:myCodeLibrary.dll /t:library myCode.vb  
```  
  
## 참고 항목  
 [어셈블리 만들기](../../../docs/framework/app-domains/create-assemblies.md)   
 [다중 파일 어셈블리](../../../docs/framework/app-domains/multifile-assemblies.md)   
 [방법: 다중 파일 어셈블리 빌드](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)   
 [어셈블리를 사용한 프로그래밍](../../../docs/framework/app-domains/programming-with-assemblies.md)