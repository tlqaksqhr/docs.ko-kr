---
title: '복사 및 업데이트가 레코드 식 (F #)'
description: 작성 한 '복사 및 업데이트 레코드 식' 복사는 기존 레코드를 업데이트 하는 필드를 지정 및 업데이트 된 레코드를 반환 하는 방법에 알아봅니다.
author: ChrSteinert
ms.date: 06/04/2016
ms.openlocfilehash: 000746b6e76349ae6d8f338519a58034f4e29020
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563061"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="5eeef-103">레코드 식 복사 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="5eeef-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="5eeef-104">A *복사 및 업데이트 레코드 식* 기존 레코드를 복사, 지정 된 필드를 업데이트 및 업데이트 된 레코드를 반환 하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="5eeef-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>


## <a name="syntax"></a><span data-ttu-id="5eeef-105">구문</span><span class="sxs-lookup"><span data-stu-id="5eeef-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a><span data-ttu-id="5eeef-106">설명</span><span class="sxs-lookup"><span data-stu-id="5eeef-106">Remarks</span></span>
<span data-ttu-id="5eeef-107">레코드를 기존 레코드 업데이트가 가능한 인수가 있도록 기본적으로 변경할 수 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eeef-107">Records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="5eeef-108">업데이트 된 레코드는 레코드의 모든 필드를 만들려면 해야 다시 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eeef-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="5eeef-109">이 작업을 간소화 하기 위해는 *복사 및 업데이트 레코드 식* 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eeef-109">To simplify this task a *copy and update record expression* can be used.</span></span> <span data-ttu-id="5eeef-110">이 식은 기존 레코드는 사용, 식에서 지정 된 필드와 식으로 지정 된 누락 된 필드를 사용 하 여 동일한 유형의 새 브러시를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5eeef-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>
<span data-ttu-id="5eeef-111">기존 레코드를 복사 하 고 필드 값의 일부를 변경 해야 할 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eeef-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="5eeef-112">사용 예를 들어 새로 만든된 레코드.</span><span class="sxs-lookup"><span data-stu-id="5eeef-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="5eeef-113">사용 하면 해당 레코드의 필드에 대해서만 업데이트 하는 경우는 *복사 및 업데이트 레코드 식* 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5eeef-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="5eeef-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5eeef-114">See Also</span></span>
[<span data-ttu-id="5eeef-115">레코드</span><span class="sxs-lookup"><span data-stu-id="5eeef-115">Records</span></span>](records.md)

[<span data-ttu-id="5eeef-116">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="5eeef-116">F# Language Reference</span></span>](index.md)
