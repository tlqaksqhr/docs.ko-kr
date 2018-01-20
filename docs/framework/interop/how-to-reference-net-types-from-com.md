---
title: "방법: COM에서 .NET 형식 참조"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
helpviewer_keywords:
- importing type library
- COM interop, referencing .NET types
- interoperation with unmanaged code, referencing .NET types
- referencing .NET types
- interoperation with unmanaged code, importing type library
- type libraries
- COM interop, importing type library
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b452dd686286ba0ddf648ee532e67a0c121f66eb
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-reference-net-types-from-com"></a><span data-ttu-id="ec16e-102">방법: COM에서 .NET 형식 참조</span><span class="sxs-lookup"><span data-stu-id="ec16e-102">How to: Reference .NET Types from COM</span></span>
<span data-ttu-id="ec16e-103">클라이언트 및 서버 코드의 관점에서 COM과 .NET Framework의 차이점은 크게 눈에 띄지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec16e-103">From the point of view of client and server code, the differences between COM and the .NET Framework are largely invisible.</span></span> <span data-ttu-id="ec16e-104">Microsoft Visual Basic 클라이언트는 개체 메서드와 구문, 속성 및 필드를 정확히 다른 COM 개체인 것처럼 노출하는 개체 브라우저에서 .NET 개체를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec16e-104">Microsoft Visual Basic clients can view a .NET object in the object browser, which exposes the object methods and syntax, properties, and fields exactly as if it were any other COM object.</span></span>  
  
 <span data-ttu-id="ec16e-105">동일한 도구를 사용하여 메타데이터를 COM 형식 라이브러리로 내보내지만 C++ 클라이언트의 경우 형식 라이브러리를 가져오는 프로세스가 약간 더 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="ec16e-105">The process for importing a type library is slightly more complicated for C++ clients, although you use the same tools to export metadata to a COM type library.</span></span> <span data-ttu-id="ec16e-106">관리되지 않는 C++ 클라이언트에서 .NET 개체 멤버를 참조하려면 **#import** 지시문을 사용하여 TLB 파일(Tlbexp.exe로 생성됨)을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="ec16e-106">To reference .NET object members from an unmanaged C++ client, reference the TLB file (produced with Tlbexp.exe) with the **#import** directive.</span></span> <span data-ttu-id="ec16e-107">C++에서 형식 라이브러리를 참조할 경우 **raw_interfaces_only** 옵션을 지정하거나 기본 클래스 라이브러리 Mscorlib.tlb의 정의를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec16e-107">When referencing a type library from C++, you must either specify the **raw_interfaces_only** option or import the definitions in the base class library, Mscorlib.tlb.</span></span>  
  
### <a name="to-import-a-library"></a><span data-ttu-id="ec16e-108">라이브러리를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="ec16e-108">To import a library</span></span>  
  
-   <span data-ttu-id="ec16e-109">**#import** 지시문에서 **raw_interfaces_only** 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec16e-109">Specify the **raw_interfaces_only** option in the **#import** directive.</span></span> <span data-ttu-id="ec16e-110">예:</span><span class="sxs-lookup"><span data-stu-id="ec16e-110">For example:</span></span>  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     <span data-ttu-id="ec16e-111">또는</span><span class="sxs-lookup"><span data-stu-id="ec16e-111">-or-</span></span>  
  
-   <span data-ttu-id="ec16e-112">Mscorlib.tlb에 대한 #import 지시문을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ec16e-112">Include an #import directive for Mscorlib.tlb.</span></span> <span data-ttu-id="ec16e-113">예:</span><span class="sxs-lookup"><span data-stu-id="ec16e-113">For example:</span></span>  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ec16e-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec16e-114">See Also</span></span>  
 [<span data-ttu-id="ec16e-115">.NET Framework 구성 요소를 COM에 노출</span><span class="sxs-lookup"><span data-stu-id="ec16e-115">Exposing .NET Framework Components to COM</span></span>](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 [<span data-ttu-id="ec16e-116">COM에 어셈블리 등록</span><span class="sxs-lookup"><span data-stu-id="ec16e-116">Registering Assemblies with COM</span></span>](../../../docs/framework/interop/registering-assemblies-with-com.md)  
 [<span data-ttu-id="ec16e-117">.NET 개체를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ec16e-117">Calling a .NET Object</span></span>](http://msdn.microsoft.com/library/40c9626c-aea6-4bad-b8f0-c1de462efd33)  
 [<span data-ttu-id="ec16e-118">COM 액세스를 위해 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="ec16e-118">Deploying an Application for COM Access</span></span>](http://msdn.microsoft.com/library/fb63564c-c1b9-4655-a094-a235625882ce)
