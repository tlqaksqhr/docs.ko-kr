---
title: "상호 운용성(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- COM interop
- interoperability
- platform invoke, accessing APIs with C#
- C# language, interoperability
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
caps.latest.revision: "31"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2965543066b0846a6a4f8a3199590049947122f2
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2017
---
# <a name="interoperability-c-programming-guide"></a><span data-ttu-id="16d43-102">상호 운용성(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="16d43-102">Interoperability (C# Programming Guide)</span></span>
<span data-ttu-id="16d43-103">상호 운용성은 비관리 코드에 대한 기존 투자를 보존하고 활용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="16d43-103">Interoperability enables you to preserve and take advantage of existing investments in unmanaged code.</span></span> <span data-ttu-id="16d43-104">CLR(공용 언어 런타임)의 제어 하에서 실행되는 코드를 *관리 코드*라고 하고, CLR 외부에서 실행되는 코드를 *비관리 코드*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="16d43-104">Code that runs under the control of the common language runtime (CLR) is called *managed code*, and code that runs outside the CLR is called *unmanaged code*.</span></span> <span data-ttu-id="16d43-105">COM, COM+, C++ 구성 요소, ActiveX 구성 요소 및 Microsoft Win32 API는 비관리 코드의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="16d43-105">COM, COM+, C++ components, ActiveX components, and Microsoft Win32 API are examples of unmanaged code.</span></span>  
  
 <span data-ttu-id="16d43-106">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]에서는 플랫폼 호출 서비스, <xref:System.Runtime.InteropServices> 네임스페이스, C++ 상호 운용성 및 COM 상호 운용성(COM interop)을 통해 비관리 코드와의 상호 운용이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="16d43-106">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] enables interoperability with unmanaged code through platform invoke services, the <xref:System.Runtime.InteropServices> namespace, C++ interoperability, and COM interoperability (COM interop).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="16d43-107">단원 내용</span><span class="sxs-lookup"><span data-stu-id="16d43-107">In This Section</span></span>  
 [<span data-ttu-id="16d43-108">상호 운용성 개요</span><span class="sxs-lookup"><span data-stu-id="16d43-108">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 <span data-ttu-id="16d43-109">C# 관리 코드와 비관리 코드 간에 상호 운용되도록 하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16d43-109">Describes methods to interoperate between C# managed code and unmanaged code.</span></span>  
  
 [<span data-ttu-id="16d43-110">방법: Visual C# 기능을 사용하여 Office Interop 개체에 액세스</span><span class="sxs-lookup"><span data-stu-id="16d43-110">How to: Access Office Interop Objects by Using Visual C# Features</span></span>](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)  
 <span data-ttu-id="16d43-111">Office 프로그래밍을 용이하게 하도록 Visual C#에 도입된 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16d43-111">Describes features that are introduced in Visual C# to facilitate Office programming.</span></span>  
  
 [<span data-ttu-id="16d43-112">방법: COM Interop 프로그래밍에서 인덱싱된 속성 사용</span><span class="sxs-lookup"><span data-stu-id="16d43-112">How to: Use Indexed Properties in COM Interop Programming</span></span>](../../../csharp/programming-guide/interop/how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 <span data-ttu-id="16d43-113">인덱싱된 속성을 사용하여 매개 변수가 있는 COM 속성에 액세스하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16d43-113">Describes how to use indexed properties to access COM properties that have parameters.</span></span>  
  
 [<span data-ttu-id="16d43-114">방법: 플랫폼 호출을 사용하여 웨이브 파일 재생</span><span class="sxs-lookup"><span data-stu-id="16d43-114">How to: Use Platform Invoke to Play a Wave File</span></span>](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md)  
 <span data-ttu-id="16d43-115">플랫폼 호출 서비스를 사용하여 Windows 운영 체제에서 .wav 사운드 파일을 재생하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16d43-115">Describes how to use platform invoke services to play a .wav sound file on the Windows operating system.</span></span>  
  
 [<span data-ttu-id="16d43-116">연습: Office 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="16d43-116">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)  
 <span data-ttu-id="16d43-117">Excel 통합 문서와 통합 문서에 대한 링크를 포함하는 Word 문서를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="16d43-117">Shows how to create an Excel workbook and a Word document that contains a link to the workbook.</span></span>  
  
 [<span data-ttu-id="16d43-118">COM 클래스 예제</span><span class="sxs-lookup"><span data-stu-id="16d43-118">Example COM Class</span></span>](../../../csharp/programming-guide/interop/example-com-class.md)  
 <span data-ttu-id="16d43-119">C# 클래스를 COM 개체로 노출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="16d43-119">Demonstrates how to expose a C# class as a COM object.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="16d43-120">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="16d43-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="16d43-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16d43-121">See Also</span></span>  
 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="16d43-122">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="16d43-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="16d43-123">비관리 코드와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="16d43-123">Interoperating with Unmanaged Code</span></span>](../../../../docs/framework/interop/index.md)  
 [<span data-ttu-id="16d43-124">연습: Office 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="16d43-124">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)
