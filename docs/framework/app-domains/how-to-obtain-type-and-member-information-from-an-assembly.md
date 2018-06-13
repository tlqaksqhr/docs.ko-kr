---
title: '방법: 어셈블리에서 형식 및 멤버 정보 가져오기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- obtaining assembly information
- assemblies [.NET Framework], obtaining information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fb06555f18c13f87347a5a76e6f4a3060777f02
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744069"
---
# <a name="how-to-obtain-type-and-member-information-from-an-assembly"></a><span data-ttu-id="657e2-102">방법: 어셈블리에서 형식 및 멤버 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="657e2-102">How to: Obtain Type and Member Information from an Assembly</span></span>
<span data-ttu-id="657e2-103"><xref:System.Reflection> 네임스페이스에는 어셈블리에서 정보를 가져오는 다양한 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="657e2-103">The <xref:System.Reflection> namespace contains many methods for obtaining information from an assembly.</span></span> <span data-ttu-id="657e2-104">이 섹션에서는 이러한 메서드 중 하나를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="657e2-104">This section demonstrates one of these methods.</span></span> <span data-ttu-id="657e2-105">자세한 내용은 [리플렉션 개요](../../../docs/framework/reflection-and-codedom/reflection.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="657e2-105">For additional information, see [Reflection Overview](../../../docs/framework/reflection-and-codedom/reflection.md).</span></span>  
  
 <span data-ttu-id="657e2-106">다음 예제에서는 어셈블리에서 형식 및 멤버 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="657e2-106">The following example obtains type and member information from an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="657e2-107">예</span><span class="sxs-lookup"><span data-stu-id="657e2-107">Example</span></span>  
 [!code-cpp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source6.cpp#8)]
 [!code-csharp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source6.cs#8)]
 [!code-vb[Conceptual.Types.ViewInfo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source6.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="657e2-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="657e2-108">See Also</span></span>  
 <span data-ttu-id="657e2-109">[응용 프로그램 도메인으로 프로그래밍](./application-domains.md#programming-with-application-domains) [리플렉션](../../../docs/framework/reflection-and-codedom/reflection.md)</span><span class="sxs-lookup"><span data-stu-id="657e2-109">[Programming with Application Domains](./application-domains.md#programming-with-application-domains) [Reflection](../../../docs/framework/reflection-and-codedom/reflection.md)</span></span>  
 [<span data-ttu-id="657e2-110">응용 프로그램 도메인 사용</span><span class="sxs-lookup"><span data-stu-id="657e2-110">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)
