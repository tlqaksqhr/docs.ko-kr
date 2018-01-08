---
title: "완화: XML 스키마 유효성 검사"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9cd5e83da32e32b60f5d1584c7057e36a3851b8b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="mitigation-xml-schema-validation"></a><span data-ttu-id="15ee8-102">완화: XML 스키마 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="15ee8-102">Mitigation: XML Schema Validation</span></span>
<span data-ttu-id="15ee8-103">[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]에서 복합 키를 사용하고 한 개의 키가 비어 있는 경우 XSD 스키마 유효성 검사가 고유한 제약 조건 위반을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="15ee8-103">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], XSD schema validation detects a violation of the unique constraint if a compound key is used and one key is empty.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="15ee8-104">영향</span><span class="sxs-lookup"><span data-stu-id="15ee8-104">Impact</span></span>  
 <span data-ttu-id="15ee8-105">이 변경에 따른 영향이 최소화되어야 합니다. 빈 키가 포함된 복합 키를 사용함으로써 `xsd:unique`가 위반된 경우 스키마 사양에 따라 스키마 유효성 검사 오류가 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="15ee8-105">The impact of this change should be minimal: based on the schema specification, a schema validation error is expected if `xsd:unique` is violated by using a compound key with an empty key.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="15ee8-106">완화</span><span class="sxs-lookup"><span data-stu-id="15ee8-106">Mitigation</span></span>  
 <span data-ttu-id="15ee8-107">복합 키에 한 개의 빈 키가 있는 경우 스키마 유효성 검사 오류 검색 여부는 구성 가능한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="15ee8-107">Whether a schema validation error is detected if a compound key has one empty key is a configurable feature:</span></span>  
  
-   <span data-ttu-id="15ee8-108">[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]을 대상으로 하는 앱부터 스키마 유효성 검사 오류 검색은 기본적으로 사용하도록 설정되어 있습니다. 그러나 스키마 유효성 검사 오류가 검색되지 않도록 이 기능을 옵트아웃(opt out)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ee8-108">Starting with the apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], detection of the schema validation error is enabled by default; however, it is possible to opt out of it, so that the schema validation error will not be detected.</span></span>  
  
-   <span data-ttu-id="15ee8-109">[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]에서 실행되지만 [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] 및 이전 버전을 대상으로 하는 앱에서는 스키마 유효성 검사 오류가 기본적으로 검색되지 않습니다. 그러나 스키마 유효성 검사 오류가 검색되도록 이 기능을 옵트인(opt in)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ee8-109">In apps that run under the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] but target the [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] and earlier versions, a schema validation error is not detected by default; however, it is possible to opt into it, so that the schema validation error will be detected.</span></span>  
  
 <span data-ttu-id="15ee8-110">이 동작은 <xref:System.AppContext> 클래스를 사용하여 `System.Xml.IgnoreEmptyKeySequences` 스위치의 값을 정의하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ee8-110">This behavior can be configured by using the <xref:System.AppContext> class to define the value of the `System.Xml.IgnoreEmptyKeySequences` switch.</span></span> <span data-ttu-id="15ee8-111">스위치의 기본값은 `false`(빈 키 시퀀스가 무시되지 않음)이기 때문에 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]을 대상으로 하는 앱은 다음 코드를 사용하여 스위치의 값을 `true`로 설정하면 해당 동작을 옵트아웃(opt out)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ee8-111">Because the switch's default value is `false` (empty key sequences are not ignored), apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] can opt out of the behavior by using the following code to set the switch's value to `true`:</span></span>  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]  
  
 <span data-ttu-id="15ee8-112">[!INCLUDE[net_v452](../../../includes/net-v452-md.md)] 및 이전 버전을 대상으로 하는 앱의 경우 스위치의 기본값이`true`(빈 키 시퀀스가 무시됨)이기 때문에 다음 코드를 사용하여 스위치의 값을 `false`로 설정하면 빈 키가 포함된 복합 키가 스키마 유효성 검사 오류를 생성하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ee8-112">For apps that target the [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] and earlier versions, because the switch's default value is `true` (empty key sequences are ignored), it is possible to ensure that a compound key with an empty key does generate a schema validation error by using the following code to set the switch's value to `false`.</span></span>  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="15ee8-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15ee8-113">See Also</span></span>  
 [<span data-ttu-id="15ee8-114">대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="15ee8-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
