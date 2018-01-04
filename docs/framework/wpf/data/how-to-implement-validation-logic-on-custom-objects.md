---
title: "방법: 사용자 지정 개체의 유효성 검사 논리 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- checking for validation errors [WPF]
- validation errors [WPF], checking for
- implementing validation logic on custom objects [WPF]
- custom objects [WPF], implementing validation logic on
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5044339e1d06bddad05151b2db99d5f96d068e77
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a><span data-ttu-id="f3e81-102">방법: 사용자 지정 개체의 유효성 검사 논리 구현</span><span class="sxs-lookup"><span data-stu-id="f3e81-102">How to: Implement Validation Logic on Custom Objects</span></span>
<span data-ttu-id="f3e81-103">이 예제에서는 사용자 지정 개체에서 유효성 검사 논리를 구현 하 여 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3e81-103">This example shows how to implement validation logic on a custom object and then bind to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3e81-104">예</span><span class="sxs-lookup"><span data-stu-id="f3e81-104">Example</span></span>  
 <span data-ttu-id="f3e81-105">소스 개체가 구현 하는 경우 비즈니스 계층에 유효성 검사 논리를 제공할 수 있습니다 <xref:System.ComponentModel.IDataErrorInfo>다음 예제와 같이,:</span><span class="sxs-lookup"><span data-stu-id="f3e81-105">You can provide validation logic on the business layer if your source object implements <xref:System.ComponentModel.IDataErrorInfo>, as in the following example:</span></span>  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 <span data-ttu-id="f3e81-106">다음 예에서는 입력란의 텍스트 속성에 바인딩됩니다는 `Age` 속성의는 `Person` 바인딩에 지정 된 리소스 선언을 통해 사용할 수 있는 개체는 `x:Key``data`합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e81-106">In the following example, the text property of the text box binds to the `Age` property of the `Person` object, which has been made available for binding through a resource declaration that is given the `x:Key``data`.</span></span> <span data-ttu-id="f3e81-107"><xref:System.Windows.Controls.DataErrorValidationRule> 에 의해 발생 하는 유효성 검사 오류에 대 한 검사는 <xref:System.ComponentModel.IDataErrorInfo> 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e81-107">The <xref:System.Windows.Controls.DataErrorValidationRule> checks for the validation errors raised by the <xref:System.ComponentModel.IDataErrorInfo> implementation.</span></span>  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml#boundtextbox)]  
  
 <span data-ttu-id="f3e81-108">사용 하는 대신 또는 <xref:System.Windows.Controls.DataErrorValidationRule>를 설정할 수 있습니다는 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e81-108">Alternatively, instead of using the <xref:System.Windows.Controls.DataErrorValidationRule>, you can set the <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3e81-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3e81-109">See Also</span></span>  
 <xref:System.Windows.Controls.ExceptionValidationRule>  
 [<span data-ttu-id="f3e81-110">바인딩 유효성 검사 구현</span><span class="sxs-lookup"><span data-stu-id="f3e81-110">Implement Binding Validation</span></span>](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [<span data-ttu-id="f3e81-111">방법 항목</span><span class="sxs-lookup"><span data-stu-id="f3e81-111">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
