---
title: "쿼리 개념"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a125749-ccb5-49d5-999d-d2db7171d74d
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 14be34b5d988a51a4785defbfcec95a4a073cc2c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="query-concepts"></a><span data-ttu-id="c11b5-102">쿼리 개념</span><span class="sxs-lookup"><span data-stu-id="c11b5-102">Query Concepts</span></span>
<span data-ttu-id="c11b5-103">이 단원에서는 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]의 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리 다지인에 대한 주요 개념을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b5-103">This section describes key concepts for designing [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c11b5-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="c11b5-104">In This Section</span></span>  
 [<span data-ttu-id="c11b5-105">LINQ to SQL 쿼리</span><span class="sxs-lookup"><span data-stu-id="c11b5-105">LINQ to SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-queries.md)  
 <span data-ttu-id="c11b5-106">일반적인 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 항목 및 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 특정 항목에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b5-106">Refers to general [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] topics, and explains items specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="c11b5-107">관계 간 쿼리</span><span class="sxs-lookup"><span data-stu-id="c11b5-107">Querying Across Relationships</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md)  
 <span data-ttu-id="c11b5-108">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 개체 모델에서 연결을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b5-108">Explains how to use associations in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="c11b5-109">원격 쿼리 실행과 로컬 실행</span><span class="sxs-lookup"><span data-stu-id="c11b5-109">Remote vs. Local Execution</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/remote-vs-local-execution.md)  
 <span data-ttu-id="c11b5-110">쿼리 실행 위치를 지정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b5-110">Explains how to specify where you want your query executed.</span></span>  
  
 [<span data-ttu-id="c11b5-111">지연 된 실행과 즉시 로드 비교</span><span class="sxs-lookup"><span data-stu-id="c11b5-111">Deferred versus Immediate Loading</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)  
 <span data-ttu-id="c11b5-112">관련 개체의 로드 시점을 지정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b5-112">Describes how to specify when related objects are loaded.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c11b5-113">관련 단원</span><span class="sxs-lookup"><span data-stu-id="c11b5-113">Related Sections</span></span>  
 [<span data-ttu-id="c11b5-114">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="c11b5-114">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="c11b5-115">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 기술을 설명하는 항목에 대한 링크가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b5-115">Contains links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology.</span></span>  
  
 [<span data-ttu-id="c11b5-116">개체 Id</span><span class="sxs-lookup"><span data-stu-id="c11b5-116">Object Identity</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/object-identity.md)  
 <span data-ttu-id="c11b5-117">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 개체 ID에 대한 개념을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b5-117">Explains the concept of object identity in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="c11b5-118">LINQ 쿼리 소개(C#)</span><span class="sxs-lookup"><span data-stu-id="c11b5-118">Introduction to LINQ Queries (C#)</span></span>](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="c11b5-119">[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]의 쿼리 작업에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b5-119">Provides an introduction to query operations in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>
