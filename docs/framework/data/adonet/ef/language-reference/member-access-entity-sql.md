---
title: "입니다. (멤버 액세스)(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 36699b403241e9a5496e722e81c833be0ed63101
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="-member-access-entity-sql"></a><span data-ttu-id="c9e07-103">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e07-103">.</span></span> <span data-ttu-id="c9e07-104">(멤버 액세스)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c9e07-104">(Member Access) (Entity SQL)</span></span>
<span data-ttu-id="c9e07-105">점 (.) 연산자는는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 멤버 액세스 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e07-105">The dot operator (.) is the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] member access operator.</span></span> <span data-ttu-id="c9e07-106">멤버 액세스 연산자를 사용하여 구조 개념적 모델 형식 인스턴스의 속성 또는 필드 값을 구합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e07-106">You use the member access operator to yield the value of a property or field of an instance of structural conceptual model type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9e07-107">구문</span><span class="sxs-lookup"><span data-stu-id="c9e07-107">Syntax</span></span>  
  
```  
expression.identifier  
```  
  
## <a name="arguments"></a><span data-ttu-id="c9e07-108">인수</span><span class="sxs-lookup"><span data-stu-id="c9e07-108">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="c9e07-109">구조 개념적 모델 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e07-109">An instance of a structural conceptual model type.</span></span>  
  
 `identifier`  
 <span data-ttu-id="c9e07-110">개체 인스턴스에 속하는 속성 또는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e07-110">A property or field that belongs to an object instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9e07-111">설명</span><span class="sxs-lookup"><span data-stu-id="c9e07-111">Remarks</span></span>  
 <span data-ttu-id="c9e07-112">점 연산자(.)는 복합 형식 또는 엔터티 형식의 속성을 추출하는 것과 유사하게 레코드에서 필드를 추출하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e07-112">The dot (.) operator may be used to extract fields from a record, similar to extracting properties of a complex or entity type.</span></span> <span data-ttu-id="c9e07-113">예를 들어 Name 형식의 n이 Person 형식의 멤버이고 p가 Person 형식의 인스턴스인 경우, p.n은 Name 형식의 값을 제공하는 유효한 멤버 액세스 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e07-113">For example, if n of type Name is a member of type Person, and p is an instance of type Person, then p.n is a legal member access expression that yields a value of type Name.</span></span>  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a><span data-ttu-id="c9e07-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9e07-114">See Also</span></span>  
 [<span data-ttu-id="c9e07-115">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="c9e07-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
