---
title: "상속 지원"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e15f0194586cc8d4e069f04a95089cbef709581f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="inheritance-support"></a><span data-ttu-id="0009c-102">상속 지원</span><span class="sxs-lookup"><span data-stu-id="0009c-102">Inheritance Support</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="0009c-103">지원 *단일 테이블 매핑*합니다.</span><span class="sxs-lookup"><span data-stu-id="0009c-103"> supports *single-table mapping*.</span></span> <span data-ttu-id="0009c-104">즉, 완전한 상속 계층이 단일 데이터베이스 테이블에 저장되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0009c-104">In other words, a complete inheritance hierarchy is stored in a single database table.</span></span> <span data-ttu-id="0009c-105">테이블에는 계층 전체에 대한 모든 가능한 데이터 열의 결합된 공용 구조체가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0009c-105">The table contains the flattened union of all possible data columns for the whole hierarchy.</span></span> <span data-ttu-id="0009c-106">공용 구조체는 두 개의 테이블을 이들 원래 테이블 중 어느 하나에 있는 행을 포함하는 하나의 테이블로 결합한 결과를 말합니다. 각 행은 행에 의해 표시되는 인스턴스 형식에 적용되지 않는 null을 열에 갖고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0009c-106">(A union is the result of combining two tables into one table that has the rows that were present in either of the original tables.) Each row has nulls in the columns that do not apply to the type of the instance represented by the row.</span></span>  
  
 <span data-ttu-id="0009c-107">단일 테이블 매핑 전략은 상속을 나타내는 가장 간단한 방법이며 여러 다른 쿼리 범주에 대한 탁월한 성능 특징을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0009c-107">The single-table mapping strategy is the simplest representation of inheritance and provides good performance characteristics for many different categories of queries.</span></span>  
  
 <span data-ttu-id="0009c-108">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 이 매핑을 구현하려면 상속 계층의 루트 클래스에서 특성 및 특성 속성을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0009c-108">To implement this mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you must specify the attributes and attribute properties on the root class of the inheritance hierarchy.</span></span> <span data-ttu-id="0009c-109">자세한 내용은 참조 [하는 방법: 상속 계층 구조 매핑](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0009c-109">For more information, see [How to: Map Inheritance Hierarchies](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).</span></span>  
  
 <span data-ttu-id="0009c-110">[!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 사용하는 개발자들은 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]로 상속 계층을 매핑할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0009c-110">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can also use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map inheritance hierarchies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0009c-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0009c-111">See Also</span></span>  
 [<span data-ttu-id="0009c-112">배경 정보</span><span class="sxs-lookup"><span data-stu-id="0009c-112">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
