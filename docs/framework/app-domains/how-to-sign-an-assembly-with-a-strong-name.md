---
title: '방법: 강력한 이름으로 어셈블리 서명'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strong-named assemblies, signing with strong names
- signing assemblies
- assemblies [.NET Framework], signing
- assemblies [.NET Framework], strong-named
ms.assetid: 2c30799a-a826-46b4-a25d-c584027a6c67
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45f8ad3bd9226ffd821fc792cdd4d0a6dac1a414
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744631"
---
# <a name="how-to-sign-an-assembly-with-a-strong-name"></a><span data-ttu-id="1230d-102">방법: 강력한 이름으로 어셈블리 서명</span><span class="sxs-lookup"><span data-stu-id="1230d-102">How to: Sign an Assembly with a Strong Name</span></span>
<span data-ttu-id="1230d-103">강력한 이름으로 어셈블리에 서명하는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-103">There are a number of ways to sign an assembly with a strong name:</span></span>  
  
-   <span data-ttu-id="1230d-104">Visual Studio에서 프로젝트의 **속성** 대화 상자에서 **서명** 탭을 사용하는 방법.</span><span class="sxs-lookup"><span data-stu-id="1230d-104">By using the **Signing** tab in a project's **Properties** dialog box in Visual Studio.</span></span> <span data-ttu-id="1230d-105">이는 가장 쉽고 편리하게 강력한 이름으로 어셈블리에 서명하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-105">This is the easiest and most convenient way to sign an assembly with a strong name.</span></span>  
  
-   <span data-ttu-id="1230d-106">[어셈블리 링커(Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) 를 사용하여 .NET Framework 코드 모듈(.netmodule 파일)을 키 파일과 연결하는 방법.</span><span class="sxs-lookup"><span data-stu-id="1230d-106">By using the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to link a .NET Framework code module (a .netmodule file) with a key file.</span></span>  
  
-   <span data-ttu-id="1230d-107">어셈블리 특성을 사용하여 강력한 이름 정보를 코드에 삽입하는 방법.</span><span class="sxs-lookup"><span data-stu-id="1230d-107">By using assembly attributes to insert the strong name information into your code.</span></span> <span data-ttu-id="1230d-108">사용할 키 파일의 위치에 따라 <xref:System.Reflection.AssemblyKeyFileAttribute> 또는 <xref:System.Reflection.AssemblyKeyNameAttribute> 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-108">You can use either the <xref:System.Reflection.AssemblyKeyFileAttribute> or the <xref:System.Reflection.AssemblyKeyNameAttribute> attribute, depending on where the key file to be used is located.</span></span>  
  
-   <span data-ttu-id="1230d-109">컴파일러 옵션을 사용하는 방법.</span><span class="sxs-lookup"><span data-stu-id="1230d-109">By using compiler options.</span></span>  
  
 <span data-ttu-id="1230d-110">강력한 이름으로 어셈블리를 서명하려면 암호화 키 쌍이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-110">You must have a cryptographic key pair to sign an assembly with a strong name.</span></span> <span data-ttu-id="1230d-111">키 쌍을 만드는 방법에 대한 자세한 내용은 [방법: 공개/개인 키 쌍 만들기](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1230d-111">For more information about creating a key pair, see [How to: Create a Public-Private Key Pair](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md).</span></span>  
  
### <a name="to-create-and-sign-an-assembly-with-a-strong-name-by-using-visual-studio"></a><span data-ttu-id="1230d-112">Visual Studio를 사용하여 강력한 이름으로 어셈블리를 만들고 서명하려면</span><span class="sxs-lookup"><span data-stu-id="1230d-112">To create and sign an assembly with a strong name by using Visual Studio</span></span>  
  
1.  <span data-ttu-id="1230d-113">**솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-113">In **Solution Explorer**, open the shortcut menu for the project, and then choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="1230d-114">**서명** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-114">Choose the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="1230d-115">**어셈블리 서명** 상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-115">Select the **Sign the assembly** box.</span></span>  
  
4.  <span data-ttu-id="1230d-116">**강력한 이름 키 파일 선택** 상자에서 **\<찾아보기…>** 를 선택한 다음, 키 파일로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-116">In the **Choose a strong name key file** box, choose **\<Browse…>**, and then navigate to the key file.</span></span> <span data-ttu-id="1230d-117">새 키 파일을 만들려면 **\<새로 만들기…>** 를 선택하고 **강력한 이름 키 만들기** 대화 상자에 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-117">To create a new key file, choose **\<New…>** and enter its name in the **Create Strong Name Key** dialog box.</span></span>  
  
### <a name="to-create-and-sign-an-assembly-with-a-strong-name-by-using-the-assembly-linker"></a><span data-ttu-id="1230d-118">어셈블리 링커를 사용하여 강력한 이름으로 어셈블리를 만들고 서명하려면</span><span class="sxs-lookup"><span data-stu-id="1230d-118">To create and sign an assembly with a strong name by using the Assembly Linker</span></span>  
  
-   <span data-ttu-id="1230d-119">[Visual Studio 명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)에서 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-119">At the [Visual Studio Command Prompt](../../../docs/framework/tools/developer-command-prompt-for-vs.md), type the following command:</span></span>  
  
     <span data-ttu-id="1230d-120">**al** **/out:**\<*assemblyName*> *\<moduleName>* **/keyfile:**\<*keyfileName*></span><span class="sxs-lookup"><span data-stu-id="1230d-120">**al** **/out:**\<*assemblyName*> *\<moduleName>* **/keyfile:**\<*keyfileName*></span></span>  
  
     <span data-ttu-id="1230d-121">다음은 각 문자에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-121">where:</span></span>  
  
     <span data-ttu-id="1230d-122">*assemblyName*</span><span class="sxs-lookup"><span data-stu-id="1230d-122">*assemblyName*</span></span>  
     <span data-ttu-id="1230d-123">어셈블리 링커가 내보낼 강력하게 서명된 어셈블리(.dll 또는.exe 파일)의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-123">The name of the strongly signed assembly (a .dll or .exe file) that Assembly Linker will emit.</span></span>  
  
     <span data-ttu-id="1230d-124">*moduleName*</span><span class="sxs-lookup"><span data-stu-id="1230d-124">*moduleName*</span></span>  
     <span data-ttu-id="1230d-125">하나 이상의 형식을 포함하는 .NET Framework 코드 모듈(.netmodule 파일)의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-125">The name of a .NET Framework code module (a .netmodule file) that includes one or more types.</span></span> <span data-ttu-id="1230d-126">C# 또는 Visual Basic에서 `/target:module` 스위치로 코드를 컴파일하여 .netmodule 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-126">You can create a .netmodule file by compiling your code with the `/target:module` switch in C# or Visual Basic.</span></span>  
  
     <span data-ttu-id="1230d-127">*keyfileName*</span><span class="sxs-lookup"><span data-stu-id="1230d-127">*keyfileName*</span></span>  
     <span data-ttu-id="1230d-128">키 쌍을 포함하는 컨테이너 또는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-128">The name of the container or file that contains the key pair.</span></span> <span data-ttu-id="1230d-129">어셈블리 링커는 현재 디렉터리에 대한 관계에서 상대 경로를 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-129">Assembly Linker interprets a relative path in relationship to the current directory.</span></span>  
  
 <span data-ttu-id="1230d-130">다음 예제에서는 키 쌍 파일 `MyAssembly.dll` 를 사용하여 강력한 이름으로 어셈블리 `sgKey.snk`을 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-130">The following example signs the assembly `MyAssembly.dll` with a strong name by using the key file `sgKey.snk`.</span></span>  
  
```  
al /out:MyAssembly.dll MyModule.netmodule /keyfile:sgKey.snk  
```  
  
 <span data-ttu-id="1230d-131">이 도구에 대한 자세한 내용은 [어셈블리 링커](../../../docs/framework/tools/al-exe-assembly-linker.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1230d-131">For more information about this tool, see [Assembly Linker](../../../docs/framework/tools/al-exe-assembly-linker.md).</span></span>  
  
#### <a name="to-sign-an-assembly-with-a-strong-name-by-using-attributes"></a><span data-ttu-id="1230d-132">특성을 사용하여 강력한 이름으로 어셈블리를 서명하려면</span><span class="sxs-lookup"><span data-stu-id="1230d-132">To sign an assembly with a strong name by using attributes</span></span>  
  
1.  <span data-ttu-id="1230d-133"><xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> 또는 <xref:System.Reflection.AssemblyKeyNameAttribute> 특성을 소스 코드 모듈에 추가하고, 강력한 이름으로 어셈블리를 서명할 때 사용할 키 쌍이 포함된 컨테이너 또는 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-133">Add the <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute to your source code file, and specify the name of the file or container that contains the key pair to use when signing the assembly with a strong name.</span></span>  
  
2.  <span data-ttu-id="1230d-134">소스 코드 파일을 정상적으로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-134">Compile the source code file normally.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1230d-135">C# 및 Visual Basic 컴파일러에서는 소스 코드에 <xref:System.Reflection.AssemblyKeyFileAttribute> 또는 <xref:System.Reflection.AssemblyKeyNameAttribute> 특성이 나올 때 컴파일러 경고(각각 CS1699 및 BC41008)를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-135">The C# and Visual Basic compilers issue compiler warnings (CS1699 and BC41008, respectively) when they encounter the <xref:System.Reflection.AssemblyKeyFileAttribute> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute in source code.</span></span> <span data-ttu-id="1230d-136">이런 경고는 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-136">You can ignore the warnings.</span></span>  
  
 <span data-ttu-id="1230d-137">다음 코드 예제에서는 어셈블리가 컴파일된 디렉터리에 있는 <xref:System.Reflection.AssemblyKeyFileAttribute> 라는 키 파일과 함께 `keyfile.snk`특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-137">The following example uses the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute with a key file called `keyfile.snk`, which is located in the directory where the assembly is compiled.</span></span>  
  
 [!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)]
 [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)]
 [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]  
  
 <span data-ttu-id="1230d-138">또한, 소스 파일을 컴파일할 때 어셈블리 서명을 연기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-138">You can also delay sign an assembly when compiling your source file.</span></span> <span data-ttu-id="1230d-139">자세한 내용은 [어셈블리 서명 연기](../../../docs/framework/app-domains/delay-sign-assembly.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1230d-139">For more information, see [Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-sign-an-assembly-with-a-strong-name-by-using-the-compiler"></a><span data-ttu-id="1230d-140">컴파일러를 사용하여 강력한 이름으로 어셈블리를 서명하려면</span><span class="sxs-lookup"><span data-stu-id="1230d-140">To sign an assembly with a strong name by using the compiler</span></span>  
  
-   <span data-ttu-id="1230d-141">C# 및 Visual Basic 컴파일러에서 `/keyfile` 또는 `/delaysign` 컴파일러 옵션을 사용하거나 C++에서 `/KEYFILE` 또는 `/DELAYSIGN` 링커 옵션을 사용하여 소스 코드 파일을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-141">Compile your source code file or files with the `/keyfile` or `/delaysign` compiler option in C# and Visual Basic, or the `/KEYFILE` or `/DELAYSIGN` linker option in C++.</span></span> <span data-ttu-id="1230d-142">옵션 이름 다음에 콜론과 키 파일의 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-142">After the option name, add a colon and the name of the key file.</span></span> <span data-ttu-id="1230d-143">명령줄 컴파일러를 사용할 때, 소스 코드 파일이 포함된 디렉터리에 키 파일을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-143">When using command-line compilers, you can copy the key file to the directory that contains your source code files.</span></span>  
  
     <span data-ttu-id="1230d-144">서명 연기에 대한 자세한 내용은 [Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1230d-144">For information on delay signing, see [Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).</span></span>  
  
     <span data-ttu-id="1230d-145">다음 예제에서는 C# 컴파일러를 사용하고 키 파일 `UtilityLibrary.dll`를 사용하여 강력한 이름으로 `sgKey.snk` 어셈블리를 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="1230d-145">The following example uses the C# compiler and signs the assembly `UtilityLibrary.dll` with a strong name by using the key file `sgKey.snk`.</span></span>  
  
    ```  
    csc /t:library UtilityLibrary.cs /keyfile:sgKey.snk  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1230d-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1230d-146">See Also</span></span>  
 [<span data-ttu-id="1230d-147">강력한 이름의 어셈블리 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="1230d-147">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
 [<span data-ttu-id="1230d-148">방법: 공개/개인 키 쌍 만들기</span><span class="sxs-lookup"><span data-stu-id="1230d-148">How to: Create a Public-Private Key Pair</span></span>](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)  
 [<span data-ttu-id="1230d-149">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="1230d-149">Al.exe (Assembly Linker)</span></span>](../../../docs/framework/tools/al-exe-assembly-linker.md)  
 [<span data-ttu-id="1230d-150">어셈블리 서명 연기</span><span class="sxs-lookup"><span data-stu-id="1230d-150">Delay Signing an Assembly</span></span>](../../../docs/framework/app-domains/delay-sign-assembly.md)  
 [<span data-ttu-id="1230d-151">어셈블리 및 매니페스트 서명 관리</span><span class="sxs-lookup"><span data-stu-id="1230d-151">Managing Assembly and Manifest Signing</span></span>](/visualstudio/ide/managing-assembly-and-manifest-signing)  
 [<span data-ttu-id="1230d-152">프로젝트 디자이너, 서명 페이지</span><span class="sxs-lookup"><span data-stu-id="1230d-152">Signing Page, Project Designer</span></span>](https://msdn.microsoft.com/library/0k50fs3b)
