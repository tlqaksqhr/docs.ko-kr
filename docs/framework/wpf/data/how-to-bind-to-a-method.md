---
title: '방법: 메서드 바인딩'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding to methods using ObjectDataProvider
- binding [WPF], to methods
- methods [WPF], binding to
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
ms.openlocfilehash: 58e243812f9c2dcb65dc37bfd50d9bcfb124e4f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557097"
---
# <a name="how-to-bind-to-a-method"></a><span data-ttu-id="08d92-102">방법: 메서드 바인딩</span><span class="sxs-lookup"><span data-stu-id="08d92-102">How to: Bind to a Method</span></span>
<span data-ttu-id="08d92-103">다음 예제를 사용 하 여 메서드를 바인딩하는 방법을 보여 줍니다 <xref:System.Windows.Data.ObjectDataProvider>합니다.</span><span class="sxs-lookup"><span data-stu-id="08d92-103">The following example shows how to bind to a method using <xref:System.Windows.Data.ObjectDataProvider>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08d92-104">예제</span><span class="sxs-lookup"><span data-stu-id="08d92-104">Example</span></span>  
 <span data-ttu-id="08d92-105">이 예에서 `TemperatureScale`는 `ConvertTemp` 메서드가 있는 클래스입니다. 이 메서드에서는 두 개의 매개 변수(`double` 중 하나와 `enum` 형식 `TempType)` 중 하나)를 사용하고 지정된 값을 한 온도 눈금에서 다른 눈금으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="08d92-105">In this example, `TemperatureScale` is a class that has a method `ConvertTemp`, which takes two parameters (one of `double` and one of the `enum` type `TempType)` and converts the given value from one temperature scale to another.</span></span> <span data-ttu-id="08d92-106">다음 예제에서는 <xref:System.Windows.Data.ObjectDataProvider> 인스턴스화하는 데 사용 되는 `TemperatureScale` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="08d92-106">In the following example, an <xref:System.Windows.Data.ObjectDataProvider> is used to instantiate the `TemperatureScale` object.</span></span> <span data-ttu-id="08d92-107">`ConvertTemp` 메서드는 지정된 두 매개 변수를 사용하여 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="08d92-107">The `ConvertTemp` method is called with two specified parameters.</span></span>  
  
 [!code-xaml[BindToMethod#WindowResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 <span data-ttu-id="08d92-108">이제 메서드를 리소스로 사용할 수 있으므로, 해당 결과에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08d92-108">Now that the method is available as a resource, you can bind to its results.</span></span> <span data-ttu-id="08d92-109">다음 예제에서는 <xref:System.Windows.Controls.TextBox.Text%2A> 속성은 <xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> 의 <xref:System.Windows.Controls.ComboBox> 메서드의 두 매개 변수에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="08d92-109">In the following example, the <xref:System.Windows.Controls.TextBox.Text%2A> property of the <xref:System.Windows.Controls.TextBox> and the <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> of the <xref:System.Windows.Controls.ComboBox> are bound to the two parameters of the method.</span></span> <span data-ttu-id="08d92-110">그러면 변환될 대상 온도와 변환될 소스 온도 눈금을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08d92-110">This allows users to specify the temperature to convert and the temperature scale to convert from.</span></span> <span data-ttu-id="08d92-111"><xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> 로 설정 되어 `true` 에 바인딩할 때문에 <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> 의 속성은 <xref:System.Windows.Data.ObjectDataProvider> 인스턴스와 래핑된 개체의 속성이 아니라는 <xref:System.Windows.Data.ObjectDataProvider> (의 `TemperatureScale` 개체).</span><span class="sxs-lookup"><span data-stu-id="08d92-111">Note that <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> is set to `true` because we are binding to the <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> property of the <xref:System.Windows.Data.ObjectDataProvider> instance and not properties of the object wrapped by the <xref:System.Windows.Data.ObjectDataProvider> (the `TemperatureScale` object).</span></span>  
  
 <span data-ttu-id="08d92-112"><xref:System.Windows.Controls.ContentControl.Content%2A> 마지막 <xref:System.Windows.Controls.Label> 사용자의 콘텐츠를 변경 하는 경우 업데이트는 <xref:System.Windows.Controls.TextBox> 나 선택한은 <xref:System.Windows.Controls.ComboBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="08d92-112">The <xref:System.Windows.Controls.ContentControl.Content%2A> of the last <xref:System.Windows.Controls.Label> updates when the user modifies the content of the <xref:System.Windows.Controls.TextBox> or the selection of the <xref:System.Windows.Controls.ComboBox>.</span></span>  
  
 [!code-xaml[BindToMethod#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 <span data-ttu-id="08d92-113">변환기 `DoubleToString` double 걸리고로 문자열 변환는 <xref:System.Windows.Data.IValueConverter.Convert%2A> 방향 (변수인 바인딩 대상에 바인딩 소스의 <xref:System.Windows.Controls.TextBox.Text%2A> 속성)으로 변환 하 고는 `string` 에 `double` 에 <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> 방향입니다.</span><span class="sxs-lookup"><span data-stu-id="08d92-113">The converter `DoubleToString` takes a double and turns it into a string in the <xref:System.Windows.Data.IValueConverter.Convert%2A> direction (from the binding source to binding target, which is the <xref:System.Windows.Controls.TextBox.Text%2A> property) and converts a `string` to a `double` in the <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> direction.</span></span>  
  
 <span data-ttu-id="08d92-114">`InvalidationCharacterRule` 는 <xref:System.Windows.Controls.ValidationRule> 잘못 된 문자를 확인 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="08d92-114">The `InvalidationCharacterRule` is a <xref:System.Windows.Controls.ValidationRule> that checks for invalid characters.</span></span> <span data-ttu-id="08d92-115">빨간색 테두리가 있는 기본 오류 템플릿을 주위에서 <xref:System.Windows.Controls.TextBox>, 입력된 값을 double 값이 아닌 사용자가 알리기 위해 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="08d92-115">The default error template, which is a red border around the <xref:System.Windows.Controls.TextBox>, appears to notify users when the input value is not a double value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08d92-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08d92-116">See Also</span></span>  
 [<span data-ttu-id="08d92-117">방법 항목</span><span class="sxs-lookup"><span data-stu-id="08d92-117">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)  
 [<span data-ttu-id="08d92-118">열거형 바인딩</span><span class="sxs-lookup"><span data-stu-id="08d92-118">Bind to an Enumeration</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-an-enumeration.md)
