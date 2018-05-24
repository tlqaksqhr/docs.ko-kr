---
title: '방법: 형식 라이브러리에서 Interop 어셈블리 생성'
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aea23daff28b50678b9fa7902857fc302494c4a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a><span data-ttu-id="da1b4-102">방법: 형식 라이브러리에서 Interop 어셈블리 생성</span><span class="sxs-lookup"><span data-stu-id="da1b4-102">How to: Generate Interop Assemblies from Type Libraries</span></span>
<span data-ttu-id="da1b4-103">[형식 라이브러리 가져오기(Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)는 COM 형식 라이브러리에 포함된 coclass 및 인터페이스를 메타데이터로 변환하는 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="da1b4-103">The [Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) is a command-line tool that converts the coclasses and interfaces contained in a COM type library to metadata.</span></span> <span data-ttu-id="da1b4-104">이 도구는 형식 정보에 대한 interop 어셈블리 및 네임스페이스를 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="da1b4-104">This tool creates an interop assembly and namespace for the type information automatically.</span></span> <span data-ttu-id="da1b4-105">클래스 메타데이터가 제공된 후 관리되는 클라이언트는 COM 형식 인스턴스를 만들고 .NET 인스턴스인 것처럼 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da1b4-105">After the metadata of a class is available, managed clients can create instances of the COM type and call its methods, just as if it were a .NET instance.</span></span> <span data-ttu-id="da1b4-106">Tlbimp.exe는 전체 형식 라이브러리를 메타데이터로 즉시 변환하지만 형식 라이브러리에 정의된 형식 하위 집합에 대한 형식 정보를 생성할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da1b4-106">Tlbimp.exe converts an entire type library to metadata at once and cannot generate type information for a subset of the types defined in a type library.</span></span>  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a><span data-ttu-id="da1b4-107">형식 라이브러리에서 interop 어셈블리를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="da1b4-107">To generate an interop assembly from a type library</span></span>  
  
1.  <span data-ttu-id="da1b4-108">다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="da1b4-108">Use the following command:</span></span>  
  
     <span data-ttu-id="da1b4-109">**tlbimp** \<*type-library-file*></span><span class="sxs-lookup"><span data-stu-id="da1b4-109">**tlbimp** \<*type-library-file*></span></span>  
  
     <span data-ttu-id="da1b4-110">**/out:** 스위치를 추가하면 변경된 이름(예: LOANLib.dll)을 가진 interop 어셈블리가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="da1b4-110">Adding the **/out:** switch produces an interop assembly with an altered name, such as LOANLib.dll.</span></span> <span data-ttu-id="da1b4-111">Interop 어셈블리 이름을 변경하면 원래 COM DLL과 구별하고 중복 이름으로 인해 발생할 수 있는 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da1b4-111">Altering the interop assembly name can help distinguish it from the original COM DLL and prevent problems that can occur from having duplicate names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da1b4-112">예</span><span class="sxs-lookup"><span data-stu-id="da1b4-112">Example</span></span>  
 <span data-ttu-id="da1b4-113">다음 명령은 `Loanlib` 네임스페이스에서 Loanlib.dll 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="da1b4-113">The following command produces the Loanlib.dll assembly in the `Loanlib` namespace.</span></span>  
  
```  
tlbimp Loanlib.dll  
```  
  
 <span data-ttu-id="da1b4-114">다음 명령은 변경된 이름(LOANLib.dll)을 가진 interop 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="da1b4-114">The following command produces an interop assembly with an altered name (LOANLib.dll).</span></span>  
  
```  
tlbimp LoanLib.dll /out: LOANLib.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="da1b4-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da1b4-115">See Also</span></span>  
 [<span data-ttu-id="da1b4-116">형식 라이브러리를 어셈블리로 가져오기</span><span class="sxs-lookup"><span data-stu-id="da1b4-116">Importing a Type Library as an Assembly</span></span>](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)  
 [<span data-ttu-id="da1b4-117">.NET Framework에 COM 구성 요소 노출</span><span class="sxs-lookup"><span data-stu-id="da1b4-117">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)
