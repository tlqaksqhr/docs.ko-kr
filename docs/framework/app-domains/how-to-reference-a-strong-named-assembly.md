---
title: "방법: 강력한 이름의 어셈블리 참조"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strong-named assemblies, compile-time references
- compile-time assembly referencing
- assemblies [.NET Framework], strong-named
- assembly binding, strong-named
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: aa46bfdfe42dca9509e39d4b6218473aa00a1877
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-reference-a-strong-named-assembly"></a><span data-ttu-id="4f0ef-102">방법: 강력한 이름의 어셈블리 참조</span><span class="sxs-lookup"><span data-stu-id="4f0ef-102">How to: Reference a Strong-Named Assembly</span></span>
<span data-ttu-id="4f0ef-103">강력한 이름의 어셈블리에서 형식이나 리소스를 참조하는 프로세스는 일반적으로 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0ef-103">The process for referencing types or resources in a strong-named assembly is usually transparent.</span></span> <span data-ttu-id="4f0ef-104">컴파일 시간(초기 바인딩) 또는 런타임에 참조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0ef-104">You can make the reference either at compile time (early binding) or at run time.</span></span>  
  
 <span data-ttu-id="4f0ef-105">컴파일 시간 참조는 어셈블리에서 다른 어셈블리를 명시적으로 참조함을 컴파일러에 지정할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0ef-105">A compile-time reference occurs when you indicate to the compiler that your assembly explicitly references another assembly.</span></span> <span data-ttu-id="4f0ef-106">컴파일 시간 참조를 사용하는 경우 컴파일러가 대상으로 지정된 강력한 이름의 어셈블리의 공개 키를 자동으로 가져오고 컴파일되는 어셈블리의 어셈블리 참조에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0ef-106">When you use compile-time referencing, the compiler automatically gets the public key of the targeted strong-named assembly and places it in the assembly reference of the assembly being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f0ef-107">강력한 이름의 어셈블리는 다른 강력한 이름의 어셈블리에서 형식만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0ef-107">A strong-named assembly can only use types from other strong-named assemblies.</span></span> <span data-ttu-id="4f0ef-108">그러지 않으면 강력한 이름의 어셈블리 보안이 손상됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f0ef-108">Otherwise, the security of the strong-named assembly would be compromised.</span></span>  
  
### <a name="to-make-a-compile-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="4f0ef-109">강력한 이름의 어셈블리에 대한 컴파일 시간 참조를 만들려면</span><span class="sxs-lookup"><span data-stu-id="4f0ef-109">To make a compile-time reference to a strong-named assembly</span></span>  
  
1.  <span data-ttu-id="4f0ef-110">명령 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0ef-110">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="4f0ef-111">\<*compiler command*> **/reference:**\<*assembly name*></span><span class="sxs-lookup"><span data-stu-id="4f0ef-111">\<*compiler command*> **/reference:**\<*assembly name*></span></span>  
  
     <span data-ttu-id="4f0ef-112">이 명령에서 *compiler command*는 사용되는 언어의 컴파일러 명령이고, *assembly name*은 참조되는 어셈블리의 강력한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4f0ef-112">In this command, *compiler command* is the compiler command for the language you are using, and *assembly name* is the name of the strong-named assembly being referenced.</span></span> <span data-ttu-id="4f0ef-113">라이브러리 어셈블리를 만들기 위해 **/t:library** 옵션과 같은 다른 컴파일러 옵션을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0ef-113">You can also use other compiler options, such as the **/t:library** option for creating a library assembly.</span></span>  
  
 <span data-ttu-id="4f0ef-114">다음 예제에서는 `myAssembly.cs`라는 코드 모듈에서 `myLibAssembly.dll`이라는 강력한 이름의 어셈블리를 참조하는 `myAssembly.dll` 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4f0ef-114">The following example creates an assembly called `myAssembly.dll` that references a strong-named assembly called `myLibAssembly.dll` from a code module called `myAssembly.cs`.</span></span>  
  
```  
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  
  
### <a name="to-make-a-run-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="4f0ef-115">강력한 이름의 어셈블리에 대한 런타임 참조를 만들려면</span><span class="sxs-lookup"><span data-stu-id="4f0ef-115">To make a run-time reference to a strong-named assembly</span></span>  
  
1.  <span data-ttu-id="4f0ef-116">강력한 이름의 어셈블리에 대한 런타임 참조를 만드는 경우(예: <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 또는 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName> 메서드 사용), 참조되는 강력한 이름의 어셈블리의 표시 이름을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0ef-116">When you make a run-time reference to a strong-named assembly (for example, by using the <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> or <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName> method), you must use the display name of the referenced strong-named assembly.</span></span> <span data-ttu-id="4f0ef-117">표시 이름의 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0ef-117">The syntax of a display name is as follows:</span></span>  
  
     <span data-ttu-id="4f0ef-118">\<*assembly name*>**,** \<*version number*>**,** \<*culture*>**,** \<*public key token*></span><span class="sxs-lookup"><span data-stu-id="4f0ef-118">\<*assembly name*>**,** \<*version number*>**,** \<*culture*>**,** \<*public key token*></span></span>  
  
     <span data-ttu-id="4f0ef-119">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0ef-119">For example:</span></span>  
  
    ```  
    myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33   
    ```  
  
     <span data-ttu-id="4f0ef-120">이 예제에서 `PublicKeyToken`은 16진수 형식의 공개 키 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="4f0ef-120">In this example, `PublicKeyToken` is the hexadecimal form of the public key token.</span></span> <span data-ttu-id="4f0ef-121">문화권 값이 없는 경우 `Culture=neutral`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0ef-121">If there is no culture value, use `Culture=neutral`.</span></span>  
  
 <span data-ttu-id="4f0ef-122">다음 코드 예제에서는 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 메서드와 함께 이 정보를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4f0ef-122">The following code example shows how to use this information with the <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> method.</span></span>  
  
 <span data-ttu-id="4f0ef-123">[!code-cpp[Assembly.Load1#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.Load1/CPP/load2.cpp#3)] [!code-csharp[Assembly.Load1#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.Load1/CS/load2.cs#3)] [!code-vb[Assembly.Load1#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.Load1/VB/load2.vb#3)]</span><span class="sxs-lookup"><span data-stu-id="4f0ef-123">[!code-cpp[Assembly.Load1#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.Load1/CPP/load2.cpp#3)] [!code-csharp[Assembly.Load1#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.Load1/CS/load2.cs#3)] [!code-vb[Assembly.Load1#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.Load1/VB/load2.vb#3)]</span></span>  
  
 <span data-ttu-id="4f0ef-124">다음 [강력한 이름(Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) 명령을 사용하여 특정 어셈블리에 대한 공개 키와 공개 키 토큰의 16진수 형식을 인쇄할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0ef-124">You can print the hexadecimal format of the public key and public key token for a specific assembly by using the following [Strong Name (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) command:</span></span>  
  
 <span data-ttu-id="4f0ef-125">**sn -Tp \<** *assembly* **>**</span><span class="sxs-lookup"><span data-stu-id="4f0ef-125">**sn -Tp \<** *assembly* **>**</span></span>  
  
 <span data-ttu-id="4f0ef-126">공개 키 파일이 있는 경우 다음 명령을 대신 사용할 수 있습니다(명령줄 옵션의 대/소문자 차이 확인).</span><span class="sxs-lookup"><span data-stu-id="4f0ef-126">If you have a public key file, you can use the following command instead (note the difference in case on the command-line option):</span></span>  
  
 <span data-ttu-id="4f0ef-127">**sn -tp \<** *assembly* **>**</span><span class="sxs-lookup"><span data-stu-id="4f0ef-127">**sn -tp \<** *assembly* **>**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f0ef-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f0ef-128">See Also</span></span>  
 [<span data-ttu-id="4f0ef-129">강력한 이름의 어셈블리 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="4f0ef-129">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)

