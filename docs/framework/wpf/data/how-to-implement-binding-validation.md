---
title: "방법: 바인딩 유효성 검사 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d57fb099fa364d34b7df5c5fce792eb42079a31
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-binding-validation"></a><span data-ttu-id="3cd4c-102">방법: 바인딩 유효성 검사 구현</span><span class="sxs-lookup"><span data-stu-id="3cd4c-102">How to: Implement Binding Validation</span></span>
<span data-ttu-id="3cd4c-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 및 잘못 된 값을 입력 한 경우 사용자에 게 시각적 피드백을 제공 하는 스타일 트리거는 사용자 지정 유효성 검사 규칙에 기반 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd4c-103">This example shows how to use an <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> and a style trigger to provide visual feedback to inform the user when an invalid value is entered, based on a custom validation rule.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cd4c-104">예</span><span class="sxs-lookup"><span data-stu-id="3cd4c-104">Example</span></span>  
 <span data-ttu-id="3cd4c-105">텍스트의 콘텐츠는 <xref:System.Windows.Controls.TextBox> 에 바인딩된 다음 예제에서는 `Age` 속성 (int) 형식의 명명 된 바인딩 소스 개체의 `ods`합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd4c-105">The text content of the <xref:System.Windows.Controls.TextBox> in the following example is bound to the `Age` property (of type int) of a binding source object named `ods`.</span></span> <span data-ttu-id="3cd4c-106">바인딩이 `AgeRangeRule`이라는 유효성 검사 규칙을 사용하도록 설정되어 있으므로 숫자가 아닌 문자 또는 21보다 작거나 130보다 큰 값을 입력하면 빨간색 느낌표가 텍스트 상자 옆에 나타나고 텍스트 상자 위로 마우스를 이동하면 오류 메시지가 포함된 도구 설명이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="3cd4c-106">The binding is set up to use a validation rule named `AgeRangeRule` so that if the user enters non-numeric characters or a value that is smaller than 21 or greater than 130, a red exclamation mark appears next to the text box and a tool tip with the error message appears when the user moves the mouse over the text box.</span></span>  
  
 [!code-xaml[BindValidation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="3cd4c-107">다음 예제에서는 구현의 `AgeRangeRule`에서 상속 되 <xref:System.Windows.Controls.ValidationRule> 재정의 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="3cd4c-107">The following example shows the implementation of `AgeRangeRule`, which inherits from <xref:System.Windows.Controls.ValidationRule> and overrides the <xref:System.Windows.Controls.ValidationRule.Validate%2A> method.</span></span> <span data-ttu-id="3cd4c-108">Int32.parse() 메서드가 값에 호출되어 값에 잘못된 문자가 포함되어 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd4c-108">The Int32.Parse() method is called on the value to make sure that it does not contain any invalid characters.</span></span> <span data-ttu-id="3cd4c-109"><xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드가 반환 되는 <xref:System.Windows.Controls.ValidationResult> 인지 여부를 나타내는 값 유효한 분석 하는 동안 예외가 포착 되는 여부 및 기간 값이 하 한과 상한을 외 여부에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd4c-109">The <xref:System.Windows.Controls.ValidationRule.Validate%2A> method returns a <xref:System.Windows.Controls.ValidationResult> that indicates if the value is valid based on whether an exception is caught during the parsing and whether the age value is outside of the lower and upper bounds.</span></span>  
  
 [!code-csharp[BindValidation#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]  
  
 <span data-ttu-id="3cd4c-110">다음 예제에서는 사용자 지정 <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` 만들어지는 유효성 검사 오류가 사용자에 게 알리도록 빨간색 느낌표가 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd4c-110">The following example shows the custom <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` that creates a red exclamation mark to notify the user of a validation error.</span></span> <span data-ttu-id="3cd4c-111">컨트롤 템플릿을 사용하여 컨트롤의 모양을 다시 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd4c-111">Control templates are used to redefine the appearance of a control.</span></span>  
  
 [!code-xaml[BindValidation#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]  
  
 <span data-ttu-id="3cd4c-112">다음 예에서 같이 <xref:System.Windows.Controls.ToolTip> 라는 스타일을 사용 하 여 오류 메시지를 작성을 보여 주는 `textBoxInError`합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd4c-112">As shown in the following example, the <xref:System.Windows.Controls.ToolTip> that shows the error message is created using the style named `textBoxInError`.</span></span> <span data-ttu-id="3cd4c-113">하는 경우의 값 <xref:System.Windows.Controls.Validation.HasError%2A> 은 `true`, 현재의 도구 설명을 설정 하는 트리거 <xref:System.Windows.Controls.TextBox> 의 첫 번째 유효성 검사 오류를 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd4c-113">If the value of <xref:System.Windows.Controls.Validation.HasError%2A> is `true`, the trigger sets the tool tip of the current <xref:System.Windows.Controls.TextBox> to its first validation error.</span></span> <span data-ttu-id="3cd4c-114"><xref:System.Windows.Data.Binding.RelativeSource%2A> 로 설정 된 <xref:System.Windows.Data.RelativeSourceMode.Self>현재 요소에 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd4c-114">The <xref:System.Windows.Data.Binding.RelativeSource%2A> is set to <xref:System.Windows.Data.RelativeSourceMode.Self>, referring to the current element.</span></span>  
  
 [!code-xaml[BindValidation#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]  
  
 <span data-ttu-id="3cd4c-115">전체 예제는 [Binding Validation Sample](http://go.microsoft.com/fwlink/?LinkID=159972)(바인딩 유효성 검사 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3cd4c-115">For the complete example, see [Binding Validation Sample](http://go.microsoft.com/fwlink/?LinkID=159972).</span></span>  
  
 <span data-ttu-id="3cd4c-116">경우에 사용자 지정을 제공 하지 않으면 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 유효성 검사 오류가 있을 때 사용자에 게 시각적 피드백을 제공 하는 기본 오류 템플릿이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="3cd4c-116">Note that if you do not provide a custom <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> the default error template appears to provide visual feedback to the user when there is a validation error.</span></span> <span data-ttu-id="3cd4c-117">자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)의 “데이터 유효성 검사”를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3cd4c-117">See "Data Validation" in [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md) for more information.</span></span> <span data-ttu-id="3cd4c-118">또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]은 바인딩 소스 속성을 업데이트하는 동안 throw된 예외를 catch하는 기본 제공 유효성 검사 규칙을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd4c-118">Also, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] provides a built-in validation rule that catches exceptions that are thrown during the update of the binding source property.</span></span> <span data-ttu-id="3cd4c-119">자세한 내용은 <xref:System.Windows.Controls.ExceptionValidationRule>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3cd4c-119">For more information, see <xref:System.Windows.Controls.ExceptionValidationRule>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cd4c-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3cd4c-120">See Also</span></span>  
 [<span data-ttu-id="3cd4c-121">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="3cd4c-121">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="3cd4c-122">방법 항목</span><span class="sxs-lookup"><span data-stu-id="3cd4c-122">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
