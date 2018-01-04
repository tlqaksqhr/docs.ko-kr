---
title: "방법: 다시 호스트된 디자이너에서 유효성 검사 오류 표시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5aa8fb53-8f75-433b-bc06-7c7d33583d5d
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f08d920b59d163b23aff63dfa7ced869048e73cd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-validation-errors-in-a-rehosted-designer"></a><span data-ttu-id="610ee-102">방법: 다시 호스트된 디자이너에서 유효성 검사 오류 표시</span><span class="sxs-lookup"><span data-stu-id="610ee-102">How to: Display Validation Errors in a Rehosted Designer</span></span>
<span data-ttu-id="610ee-103">이 항목에서는 다시 호스트된 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)]에서 유효성 검사 오류를 검색하고 게시하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="610ee-103">This topic describes how to retrieve and publish validation errors in a rehosted [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].</span></span> <span data-ttu-id="610ee-104">또한 다시 호스트된 디자이너의 워크플로가 유효한지 확인하는 절차도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="610ee-104">This provides us with a procedure to confirm that a workflow in a rehosted designer is valid.</span></span>  
  
 <span data-ttu-id="610ee-105">이 작업은 두 부분으로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="610ee-105">This task has two parts.</span></span> <span data-ttu-id="610ee-106">첫 번째 부분은 <xref:System.Activities.Presentation.Validation.IValidationErrorService> 구현을 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="610ee-106">The first is to provide an implementation <xref:System.Activities.Presentation.Validation.IValidationErrorService>.</span></span>  <span data-ttu-id="610ee-107">이 인터페이스에서 구현할 중요한 메서드인 <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>가 있습니다. 이 메서드는 디버그 로그 오류에 대한 정보가 들어 있는 <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> 개체 목록을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="610ee-107">There is one critical method to implement on this interface, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> which will pass you a list of <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> objects containing information about the errors to the debug log.</span></span>  <span data-ttu-id="610ee-108">인터페이스를 구현한 후 해당 구현의 인스턴스를 편집 컨텍스트에 게시하여 오류 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="610ee-108">After implementing the interface, you retrieve the error information by publishing an instance of that implementation to the editing context.</span></span>  
  
### <a name="implement-the-ivalidationerrorservice-interface"></a><span data-ttu-id="610ee-109">IValidationErrorService 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="610ee-109">Implement the IValidationErrorService Interface</span></span>  
  
1.  <span data-ttu-id="610ee-110">다음은 유효성 검사 오류를 디버그 로그에 쓰는 간단한 구현을 위한 코드 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="610ee-110">Here is a code sample for a simple implementation that will write out the validation errors to the debug log.</span></span>  
  
    ```  
    using System.Activities.Presentation.Validation;  
    using System.Collections.Generic;  
    using System.Diagnostics;  
    using System.Linq;  
  
    namespace VariableFinderShell  
    {  
        class DebugValidationErrorService : IValidationErrorService  
        {  
            public void ShowValidationErrors(IList<ValidationErrorInfo> errors)  
            {  
                errors.ToList().ForEach(vei => Debug.WriteLine(string.Format("Error: {0} ", vei.Message)));  
            }  
        }  
    }  
    ```  
  
### <a name="publishing-to-the-editing-context"></a><span data-ttu-id="610ee-111">편집 컨텍스트에 게시</span><span class="sxs-lookup"><span data-stu-id="610ee-111">Publishing to the Editing Context</span></span>  
  
1.  <span data-ttu-id="610ee-112">다음은 이 인스턴스를 편집 컨텍스트에 게시하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="610ee-112">Here is the code that will publish this to the editing context.</span></span>  
  
    ```  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```
