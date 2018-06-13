---
title: '방법: Tlbimp.exe를 사용하여 주 Interop 어셈블리 생성'
ms.date: 03/30/2017
helpviewer_keywords:
- primary interop assemblies, generating
- Tlbimp.exe
- Type Library Importer
ms.assetid: 5419011c-6e57-40f6-8c65-386db8f7a651
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74c196c0f6525214e2ea25e6506e9c89f4e48906
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33389995"
---
# <a name="how-to-generate-primary-interop-assemblies-using-tlbimpexe"></a><span data-ttu-id="9064e-102">방법: Tlbimp.exe를 사용하여 주 Interop 어셈블리 생성</span><span class="sxs-lookup"><span data-stu-id="9064e-102">How to: Generate Primary Interop Assemblies Using Tlbimp.exe</span></span>
<span data-ttu-id="9064e-103">주 interop 어셈블리를 생성하는 다음 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-103">There are two ways to generate a primary interop assembly:</span></span>  
  
-   <span data-ttu-id="9064e-104">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]에서 제공하는 [형식 라이브러리 가져오기(Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) 사용.</span><span class="sxs-lookup"><span data-stu-id="9064e-104">Using the [Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) provided by the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span>  
  
     <span data-ttu-id="9064e-105">주 interop 어셈블리를 생성하는 가장 간단한 방법은 [Tlbimp.exe(형식 라이브러리 가져오기)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-105">The most straightforward way to produce primary interop assemblies is to use the [Tlbimp.exe (Type Library Importer)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="9064e-106">Tlbimp.exe는 다음과 같은 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-106">Tlbimp.exe provides the following safeguards:</span></span>  
  
    -   <span data-ttu-id="9064e-107">중첩된 형식 라이브러리 참조에 대한 새 interop 어셈블리를 만들기 전에 등록된 다른 주 interop 어셈블리를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-107">Checks for other registered primary interop assemblies before creating new interop assemblies for any nested type library references.</span></span>  
  
    -   <span data-ttu-id="9064e-108">컨테이너 또는 파일 이름을 지정하여 주 interop 어셈블리에 강력한 이름을 제공하지 않으면 주 interop 어셈블리를 내보내지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-108">Fails to emit the primary interop assembly if you do not specify either the container or file name to give the primary interop assembly a strong name.</span></span>  
  
    -   <span data-ttu-id="9064e-109">종속 어셈블리에 대한 참조를 생략하면 주 interop 어셈블리를 내보내지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-109">Fails to emit a primary interop assembly if you omit references to dependent assemblies.</span></span>  
  
    -   <span data-ttu-id="9064e-110">주 interop 어셈블리가 아닌 종속 어셈블리에 대한 참조를 추가하면 주 interop 어셈블리를 내보내지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-110">Fails to emit a primary interop assembly if you add references to dependent assemblies that are not primary interop assemblies.</span></span>  
  
-   <span data-ttu-id="9064e-111">C#과 같은 CLS(공용 언어 사양)를 준수하는 언어를 사용하여 소스 코드에서 수동으로 주 interop 어셈블리 만들기.</span><span class="sxs-lookup"><span data-stu-id="9064e-111">Creating primary interop assemblies manually in source code by using a language that is compliant with the Common Language Specification (CLS), such as C#.</span></span> <span data-ttu-id="9064e-112">이 접근 방식은 형식 라이브러리를 사용할 수 없는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-112">This approach is useful when a type library is unavailable.</span></span>  
  
 <span data-ttu-id="9064e-113">강력한 이름으로 어셈블리에 서명하려면 암호화 키 쌍이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-113">You must have a cryptographic key pair to sign the assembly with a strong name.</span></span> <span data-ttu-id="9064e-114">자세한 내용은 [키 쌍 만들기](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9064e-114">For details, see [Creating A Key Pair](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md).</span></span>  
  
### <a name="to-generate-a-primary-interop-assembly-using-tlbimpexe"></a><span data-ttu-id="9064e-115">Tlbimp.exe를 사용하여 주 Interop 어셈블리를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="9064e-115">To generate a primary interop assembly using Tlbimp.exe</span></span>  
  
1.  <span data-ttu-id="9064e-116">명령 프롬프트에서 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-116">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="9064e-117">**tlbimp** *tlbfile*  **/primary /keyfile:** *filename* **/out:** *assemblyname*</span><span class="sxs-lookup"><span data-stu-id="9064e-117">**tlbimp** *tlbfile*  **/primary /keyfile:** *filename* **/out:** *assemblyname*</span></span>  
  
     <span data-ttu-id="9064e-118">이 명령에서 *tlbfile*은 COM 형식 라이브러리를 포함하는 파일이고, *filename*은 키 쌍을 포함하는 컨테이너 또는 파일의 이름이고, *assemblyname*은 강력한 이름으로 서명할 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-118">In this command, *tlbfile* is the file containing the COM type library, *filename* is the name of the container or file that contains the key pair, and *assemblyname* is the name of the assembly to sign with a strong name.</span></span>  
  
 <span data-ttu-id="9064e-119">주 interop 어셈블리는 다른 주 interop 어셈블리만 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-119">Primary interop assemblies can reference only other primary interop assemblies.</span></span> <span data-ttu-id="9064e-120">어셈블리가 타사 COM 형식 라이브러리의 형식을 참조하는 경우 먼저 게시자로부터 주 interop 어셈블리를 얻어야 고유한 주 interop 어셈블리를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-120">If your assembly references types from a third-party COM type library, you must obtain a primary interop assembly from the publisher before you can generate your primary interop assembly.</span></span> <span data-ttu-id="9064e-121">게시자인 경우 참조하는 주 interop 어셈블리를 생성하기 전에 종속 형식 라이브러리에 대한 주 interop 어셈블리를 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-121">If you are the publisher, you must generate a primary interop assembly for the dependent type library before generating the referencing primary interop assembly.</span></span>  
  
 <span data-ttu-id="9064e-122">원본 형식 라이브러리와 다른 버전 번호를 가진 종속된 주 interop 어셈블리는 현재 디렉터리에 설치된 경우 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-122">A dependent primary interop assembly with a version number that differs from that of the original type library is not discoverable when installed in the current directory.</span></span> <span data-ttu-id="9064e-123">Windows 레지스트리에 종속된 주 interop 어셈블리를 등록하거나 **/reference** 옵션을 사용하여 Tlbimp.exe가 종속 DLL을 찾을 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-123">You must either register the dependent primary interop assembly in the Windows registry or use the **/reference** option to be sure that Tlbimp.exe finds the dependent DLL.</span></span>  
  
 <span data-ttu-id="9064e-124">여러 버전의 형식 라이브러리를 래핑할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-124">You can also wrap multiple versions of a type library.</span></span> <span data-ttu-id="9064e-125">자세한 내용은 [방법: 여러 버전의 형식 라이브러리 래핑](https://msdn.microsoft.com/library/79eefe04-a770-4bc3-8ea2-e90ddb8ec31f(v=vs.100))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9064e-125">For instructions, see [How to: Wrap Multiple Versions of Type Libraries](https://msdn.microsoft.com/library/79eefe04-a770-4bc3-8ea2-e90ddb8ec31f(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9064e-126">예</span><span class="sxs-lookup"><span data-stu-id="9064e-126">Example</span></span>  
 <span data-ttu-id="9064e-127">다음 예제에서는 COM 형식 라이브러리 `LibUtil.tlb`를 가져오고 키 파일 `CompanyA.snk`를 사용하여 강력한 이름으로 `LibUtil.dll` 어셈블리에 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-127">The following example imports the COM type library `LibUtil.tlb` and signs the assembly `LibUtil.dll` with a strong name using the key file `CompanyA.snk`.</span></span> <span data-ttu-id="9064e-128">이 예제에서는 특정 네임스페이스 이름을 생략하여 기본 네임스페이스 `LibUtil`을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-128">By omitting a specific namespace name, this example produces the default namespace, `LibUtil`.</span></span>  
  
```  
tlbimp LibUtil.tlb /primary /keyfile:CompanyA.snk /out:LibUtil.dll  
```  
  
 <span data-ttu-id="9064e-129">보다 설명적인 이름(*VendorName*.*LibraryName* 명명 지침 사용)을 위해 다음 예제에서는 기본 어셈블리 파일 이름 및 네임스페이스 이름을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-129">For a more descriptive name (using the *VendorName*.*LibraryName* naming guideline), the following example overrides the default assembly file name and namespace name.</span></span>  
  
```  
tlbimp LibUtil.tlb /primary /keyfile:CompanyA.snk /namespace:CompanyA.LibUtil /out:CompanyA.LibUtil.dll  
```  
  
 <span data-ttu-id="9064e-130">다음 예제에서는 `CompanyA.LibUtil.dll`을 참조하는 `MyLib.tlb`를 가져오고 키 파일 `CompanyB.snk`를 사용하여 강력한 이름으로 `CompanyB.MyLib.dll` 어셈블리에 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-130">The following example imports `MyLib.tlb`, which references `CompanyA.LibUtil.dll`, and signs the assembly `CompanyB.MyLib.dll` with a strong name using the key file `CompanyB.snk`.</span></span> <span data-ttu-id="9064e-131">`CompanyB.MyLib` 네임스페이스에서 기본 네임스페이스 이름을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9064e-131">The namespace, `CompanyB.MyLib`, overrides the default namespace name.</span></span>  
  
```  
tlbimp MyLib.tlb /primary /keyfile:CompanyB.snk /namespace:CompanyB.MyLib /reference:CompanyA.LibUtil.dll /out:CompanyB.MyLib.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="9064e-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9064e-132">See Also</span></span>  
 [<span data-ttu-id="9064e-133">방법: 주 Interop 어셈블리 등록</span><span class="sxs-lookup"><span data-stu-id="9064e-133">How to: Register Primary Interop Assemblies</span></span>](../../../docs/framework/interop/how-to-register-primary-interop-assemblies.md)
