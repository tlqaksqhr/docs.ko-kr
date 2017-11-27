---
title: "포함 된 interop 어셈블리 &#39;에 참조를 만들었습니다. &lt;assembly1&gt;&#39; 어셈블리 &#39;에서 해당 어셈블리에 간접 참조&lt; assembly2&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40059
- bc40059
helpviewer_keywords:
- VBC40059
- BC40059
ms.assetid: 520e39cb-8ab6-46f5-aa00-08afd51b4b7c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bc2fbb044fc839aa24abf3dc1ea864457efb0653
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="a-reference-was-created-to-embedded-interop-assembly-39ltassembly1gt39-because-of-an-indirect-reference-to-that-assembly-from-assembly-39ltassembly2gt39"></a><span data-ttu-id="7e5c7-102">포함 된 interop 어셈블리 &#39;에 참조를 만들었습니다. &lt;assembly1&gt;&#39; 어셈블리 &#39;에서 해당 어셈블리에 간접 참조&lt; assembly2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="7e5c7-102">A reference was created to embedded interop assembly &#39;&lt;assembly1&gt;&#39; because of an indirect reference to that assembly from assembly &#39;&lt;assembly2&gt;&#39;</span></span>
<span data-ttu-id="7e5c7-103">포함된 interop 어셈블리 ‘\<assembly1>’에 대한 참조는 해당 어셈블리에 대한 ‘\<assembly2>’ 어셈블리의 간접 참조로 인해 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="7e5c7-103">A reference was created to embedded interop assembly '\<assembly1>' because of an indirect reference to that assembly from assembly '\<assembly2>'.</span></span> <span data-ttu-id="7e5c7-104">두 어셈블리 중 하나에서 ‘Embed Interop Types’ 속성을 변경하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7e5c7-104">Consider changing the 'Embed Interop Types' property on either assembly.</span></span>  
  
 <span data-ttu-id="7e5c7-105">`Embed Interop Types` 속성이 `True`로 설정된 어셈블리(assembly1)에 대한 참조를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="7e5c7-105">You have added a reference to an assembly (assembly1) that has the `Embed Interop Types` property set to `True`.</span></span> <span data-ttu-id="7e5c7-106">이는 해당 어셈블리의 interop 형식 정보를 포함하도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="7e5c7-106">This instructs the compiler to embed interop type information from that assembly.</span></span> <span data-ttu-id="7e5c7-107">그러나 참조한 다른 어셈블리(assembly2)에서도 해당 어셈블리(assembly1)를 참조하고 `Embed Interop Types` 속성을 `False`로 설정했으므로 컴파일러에서 해당 어셈블리의 interop 형식 정보를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e5c7-107">However, the compiler cannot embed interop type information from that assembly because another assembly that you have referenced (assembly2) also references that assembly (assembly1) and has the `Embed Interop Types` property set to `False`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e5c7-108">어셈블리 참조에서 `Embed Interop Types` 속성을 `True`로 설정하는 것은 명령줄 컴파일러에 대해 `/link` 옵션을 사용하여 해당 어셈블리를 참조하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7e5c7-108">Setting the `Embed Interop Types` property on an assembly reference to `True` is equivalent to referencing the assembly by using the `/link` option for the command-line compiler.</span></span>  
  
 <span data-ttu-id="7e5c7-109">**오류 ID:** BC40059</span><span class="sxs-lookup"><span data-stu-id="7e5c7-109">**Error ID:** BC40059</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="7e5c7-110">이 경고를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="7e5c7-110">To address this warning</span></span>  
  
-   <span data-ttu-id="7e5c7-111">두 어셈블리의 interop 형식 정보를 포함하려면 assembly1에 대한 모든 참조에서 `Embed Interop Types` 속성을 `True`로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="7e5c7-111">To embed interop type information for both assemblies, set the `Embed Interop Types` property on all references to assembly1 to `True`.</span></span>  
  
-   <span data-ttu-id="7e5c7-112">경고를 제거하기 위해 assembly1의 `Embed Interop Types` 속성을 `False`로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e5c7-112">To remove the warning, you can set the `Embed Interop Types` property of assembly1 to `False`.</span></span> <span data-ttu-id="7e5c7-113">이 경우 interop 형식 정보는 주 interop 어셈블리 (PIA)에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e5c7-113">In this case, interop type information is provided by a primary interop assembly (PIA).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e5c7-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e5c7-114">See Also</span></span>  
 [<span data-ttu-id="7e5c7-115">/link(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7e5c7-115">/link (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/link.md)  
 [<span data-ttu-id="7e5c7-116">주 Interop 어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="7e5c7-116">Programming with Primary Interop Assemblies</span></span>](http://msdn.microsoft.com/en-us/306fa1d6-0703-4004-9e93-d0a57f1be81e)
