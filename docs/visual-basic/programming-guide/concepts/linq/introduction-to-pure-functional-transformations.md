---
title: "순수 함수 변환 (Visual Basic) 소개"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82bf3348-c503-4854-a91f-71f9835779ff
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 37dc4520d2ef4795ac906732b35444eeb917a814
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="introduction-to-pure-functional-transformations-visual-basic"></a><span data-ttu-id="4a917-102">순수 함수 변환 (Visual Basic) 소개</span><span class="sxs-lookup"><span data-stu-id="4a917-102">Introduction to Pure Functional Transformations (Visual Basic)</span></span>
<span data-ttu-id="4a917-103">이 단원에서는 기본 개념과 지원하는 언어 구문을 비롯하여 함수 변환에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="4a917-103">This section introduces functional transformations, including the underlying concepts and supporting language constructs.</span></span> <span data-ttu-id="4a917-104">프로그래밍에 대한 개체 지향 및 함수 변환 방법을 대조하고 함수 변환 방법으로 전환하는 방법에 대한 조언을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4a917-104">It contrasts the object-oriented and functional transformation approaches to programming, including advice on how to transition to the latter.</span></span> <span data-ttu-id="4a917-105">많은 프로그래밍 시나리오에서 함수 변환을 사용할 수 있지만 여기에서는 XML 변환이 구체적인 예제로 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4a917-105">Although functional transformations can be used in many programming scenarios, XML transformation is used here as a concrete example.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4a917-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="4a917-106">In This Section</span></span>  
  
|<span data-ttu-id="4a917-107">항목</span><span class="sxs-lookup"><span data-stu-id="4a917-107">Topic</span></span>|<span data-ttu-id="4a917-108">설명</span><span class="sxs-lookup"><span data-stu-id="4a917-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="4a917-109">개념과 용어 (함수 변환) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a917-109">Concepts and Terminology (Functional Transformation) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md)|<span data-ttu-id="4a917-110">순수 함수 변환의 개념과 용어에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="4a917-110">Introduces the concepts and terminology of pure functional transformations.</span></span>|  
|[<span data-ttu-id="4a917-111">함수형 프로그래밍과 명령형 프로그래밍 비교 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a917-111">Functional Programming vs. Imperative Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)|<span data-ttu-id="4a917-112">함수형 프로그래밍을 더욱 일반적인 명령형(절차적) 프로그래밍과 비교하고 대조합니다.</span><span class="sxs-lookup"><span data-stu-id="4a917-112">Compares and contrasts functional programming to more traditional imperative (procedural) programming.</span></span>|  
|[<span data-ttu-id="4a917-113">(Visual Basic) 순수 함수로 리팩터링</span><span class="sxs-lookup"><span data-stu-id="4a917-113">Refactoring Into Pure Functions (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md)|<span data-ttu-id="4a917-114">순수 함수에 대해 소개하고 순수 함수와 비순수 함수의 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4a917-114">Introduces pure functions, and shows examples of and pure and impure functions.</span></span>|  
|[<span data-ttu-id="4a917-115">함수 변환 (Visual Basic)의 적용 여부</span><span class="sxs-lookup"><span data-stu-id="4a917-115">Applicability of Functional Transformation (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/applicability-of-functional-transformation.md)|<span data-ttu-id="4a917-116">함수 변환의 일반적인 시나리오에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4a917-116">Describes typical scenarios for functional transformations.</span></span>|  
|[<span data-ttu-id="4a917-117">XML의 함수 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a917-117">Functional Transformation of XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/functional-transformation-of-xml.md)|<span data-ttu-id="4a917-118">XML 트리 변환 측면에서 함수 변환에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4a917-118">Describes functional transformations in the context of transforming XML trees.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4a917-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a917-119">See Also</span></span>  
 [<span data-ttu-id="4a917-120">(Visual Basic) XML의 순수 함수 변형</span><span class="sxs-lookup"><span data-stu-id="4a917-120">Pure Functional Transformations of XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)
