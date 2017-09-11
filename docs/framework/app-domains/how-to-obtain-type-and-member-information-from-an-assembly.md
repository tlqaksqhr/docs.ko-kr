---
title: "방법: 어셈블리에서 형식 및 멤버 정보 가져오기"
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
- obtaining assembly information
- assemblies [.NET Framework], obtaining information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 702567b7b05f8469f796b03a59f2ead71c0a9c22
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-obtain-type-and-member-information-from-an-assembly"></a><span data-ttu-id="020a6-102">방법: 어셈블리에서 형식 및 멤버 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="020a6-102">How to: Obtain Type and Member Information from an Assembly</span></span>
<span data-ttu-id="020a6-103"><xref:System.Reflection> 네임스페이스에는 어셈블리에서 정보를 가져오는 다양한 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="020a6-103">The <xref:System.Reflection> namespace contains many methods for obtaining information from an assembly.</span></span> <span data-ttu-id="020a6-104">이 섹션에서는 이러한 메서드 중 하나를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="020a6-104">This section demonstrates one of these methods.</span></span> <span data-ttu-id="020a6-105">자세한 내용은 [리플렉션 개요](../../../docs/framework/reflection-and-codedom/reflection.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="020a6-105">For additional information, see [Reflection Overview](../../../docs/framework/reflection-and-codedom/reflection.md).</span></span>  
  
 <span data-ttu-id="020a6-106">다음 예제에서는 어셈블리에서 형식 및 멤버 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="020a6-106">The following example obtains type and member information from an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="020a6-107">예제</span><span class="sxs-lookup"><span data-stu-id="020a6-107">Example</span></span>  
 <span data-ttu-id="020a6-108">[!code-cpp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source6.cpp#8)] [!code-csharp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source6.cs#8)] [!code-vb[Conceptual.Types.ViewInfo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source6.vb#8)]</span><span class="sxs-lookup"><span data-stu-id="020a6-108">[!code-cpp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source6.cpp#8)] [!code-csharp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source6.cs#8)] [!code-vb[Conceptual.Types.ViewInfo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source6.vb#8)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="020a6-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="020a6-109">See Also</span></span>  
 <span data-ttu-id="020a6-110">[응용 프로그램 도메인으로 프로그래밍](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131) </span><span class="sxs-lookup"><span data-stu-id="020a6-110">[Programming with Application Domains](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131) </span></span>  
 <span data-ttu-id="020a6-111">[리플렉션](../../../docs/framework/reflection-and-codedom/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="020a6-111">[Reflection](../../../docs/framework/reflection-and-codedom/reflection.md) </span></span>  
 [<span data-ttu-id="020a6-112">응용 프로그램 도메인 사용</span><span class="sxs-lookup"><span data-stu-id="020a6-112">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)

