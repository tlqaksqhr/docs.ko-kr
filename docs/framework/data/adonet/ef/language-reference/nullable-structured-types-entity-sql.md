---
title: "null 허용 구조적 형식(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 29b0aa7f6f155de2c55f88b4c796ecc482d1cb84
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="nullable-structured-types-entity-sql"></a><span data-ttu-id="c0358-102">null 허용 구조적 형식(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c0358-102">Nullable Structured Types (Entity SQL)</span></span>
<span data-ttu-id="c0358-103">구조적 형식의 `null` 인스턴스는 존재하지 않는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="c0358-103">A `null` instance of a structured type is an instance that does not exist.</span></span> <span data-ttu-id="c0358-104">이는 모든 속성에 `null` 값이 있는 기존 인스턴스와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="c0358-104">This is different from an existing instance in which all properties have `null` values.</span></span>  
  
 <span data-ttu-id="c0358-105">이 항목에서는 어떤 형식이 nullable이고 어떤 코드 패턴이 구조적 nullable 형식의 `null` 인스턴스를 생성하는지를 비롯하여 구조적 nullable형식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0358-105">This topic describes the nullable structured types, including which types are nullable and which code patterns produce `null` instances of structured nullable types.</span></span>  
  
## <a name="kinds-of-nullable-structured-types"></a><span data-ttu-id="c0358-106">구조적 Nullable 형식의 종류</span><span class="sxs-lookup"><span data-stu-id="c0358-106">Kinds of Nullable Structured Types</span></span>  
 <span data-ttu-id="c0358-107">구조적 nullable 형식에는 세 가지 종류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0358-107">There are three kinds of nullable structure types:</span></span>  
  
-   <span data-ttu-id="c0358-108">행 형식</span><span class="sxs-lookup"><span data-stu-id="c0358-108">Row types.</span></span>  
  
-   <span data-ttu-id="c0358-109">복합 형식</span><span class="sxs-lookup"><span data-stu-id="c0358-109">Complex types.</span></span>  
  
-   <span data-ttu-id="c0358-110">엔터티 형식</span><span class="sxs-lookup"><span data-stu-id="c0358-110">Entity types.</span></span>  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a><span data-ttu-id="c0358-111">구조적 형식의 Null 인스턴스를 생성하는 코드 패턴</span><span class="sxs-lookup"><span data-stu-id="c0358-111">Code Patterns that Produce Null Instances of Structured Types</span></span>  
 <span data-ttu-id="c0358-112">다음 시나리오에서는 `null` 인스턴스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c0358-112">The following scenarios produce `null` instances:</span></span>  
  
-   <span data-ttu-id="c0358-113">`null`을 구조적 형식으로 모양 결정:</span><span class="sxs-lookup"><span data-stu-id="c0358-113">Shaping `null` as a structured type:</span></span>  
  
    ```  
    TREAT (NULL AS StructuredType)  
    ```  
  
-   <span data-ttu-id="c0358-114">기본 형식을 파생 형식으로 업캐스트:</span><span class="sxs-lookup"><span data-stu-id="c0358-114">Upcasting of a base type to a derived type:</span></span>  
  
    ```  
    TREAT (BaseType AS DerivedType)  
    ```  
  
-   <span data-ttu-id="c0358-115">False 조건에 대한 외부 조인:</span><span class="sxs-lookup"><span data-stu-id="c0358-115">Outer join on false condition:</span></span>  
  
    ```  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="c0358-116">--또는</span><span class="sxs-lookup"><span data-stu-id="c0358-116">--or</span></span>  
  
    ```  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="c0358-117">--또는</span><span class="sxs-lookup"><span data-stu-id="c0358-117">--or</span></span>  
  
    ```  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
-   <span data-ttu-id="c0358-118">`null` 참조 역참조:</span><span class="sxs-lookup"><span data-stu-id="c0358-118">Dereferencing a `null` reference:</span></span>  
  
    ```  
    DEREF(NullRef)  
    ```  
  
-   <span data-ttu-id="c0358-119">빈 컬렉션에서 ANYELEMENT 가져오기:</span><span class="sxs-lookup"><span data-stu-id="c0358-119">Obtaining ANYELEMENT from an empty collection:</span></span>  
  
    ```  
    ANYELEMENT(EmptyCollection)  
    ```  
  
-   <span data-ttu-id="c0358-120">구조적 형식의 `null` 인스턴스 확인:</span><span class="sxs-lookup"><span data-stu-id="c0358-120">Checking for `null` instances of structured types:</span></span>  
  
    ```csharp  
    ...  
    for (int i = 0; i < reader.FieldCount; i++)  
    {  
        if (reader.IsDBNull(i))  
        {  
            Console.WriteLine("[NULL]");  
        }  
        else  
        {  
            Console.WriteLine(reader.GetValue(i).ToString());  
        }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c0358-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0358-121">See Also</span></span>  
 [<span data-ttu-id="c0358-122">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="c0358-122">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
