---
title: Windows Forms 컨트롤에서 속성 정의
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties [Windows Forms], defining in code
- custom controls [Windows Forms], defining properties in code
ms.assetid: c2eb8277-a842-4d99-89a9-647b901a0434
ms.openlocfilehash: dc47d7152419d55b3e52aec70257e2b39e9aaca0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528325"
---
# <a name="defining-a-property-in-windows-forms-controls"></a><span data-ttu-id="fc32e-102">Windows Forms 컨트롤에서 속성 정의</span><span class="sxs-lookup"><span data-stu-id="fc32e-102">Defining a Property in Windows Forms Controls</span></span>
<span data-ttu-id="fc32e-103">속성의 개요는 [속성 개요](http://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc32e-103">For an overview of properties, see [Properties Overview](http://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52).</span></span> <span data-ttu-id="fc32e-104">속성을 정의할 때 다음과 같은 몇 가지 주요 고려 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc32e-104">There are a few important considerations when defining a property:</span></span>  
  
-   <span data-ttu-id="fc32e-105">정의한 속성에 특성을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc32e-105">You must apply attributes to the properties you define.</span></span> <span data-ttu-id="fc32e-106">특성은 디자이너가 속성을 표시하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fc32e-106">Attributes specify how the designer should display a property.</span></span> <span data-ttu-id="fc32e-107">자세한 내용은 [구성 요소의 디자인 타임 특성](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc32e-107">For details, see [Design-Time Attributes for Components](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3).</span></span>  
  
-   <span data-ttu-id="fc32e-108">컨트롤의 시각적 표시에 영향을 주는 속성을 변경 하는 경우 호출 된 <xref:System.Windows.Forms.Control.Invalidate%2A> 메서드 (컨트롤에서 상속 되는 <xref:System.Windows.Forms.Control>)에서 `set` 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="fc32e-108">If changing the property affects the visual display of the control, call the <xref:System.Windows.Forms.Control.Invalidate%2A> method (that your control inherits from <xref:System.Windows.Forms.Control>) from the `set` accessor.</span></span> <span data-ttu-id="fc32e-109"><xref:System.Windows.Forms.Control.Invalidate%2A> 호출 하 여는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드에 컨트롤을 다시 그립니다.</span><span class="sxs-lookup"><span data-stu-id="fc32e-109"><xref:System.Windows.Forms.Control.Invalidate%2A> in turn calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method, which redraws the control.</span></span> <span data-ttu-id="fc32e-110">여러 번 호출 <xref:System.Windows.Forms.Control.Invalidate%2A> 를 한 번 호출 될 <xref:System.Windows.Forms.Control.OnPaint%2A> 효율성에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc32e-110">Multiple calls to <xref:System.Windows.Forms.Control.Invalidate%2A> result in a single call to <xref:System.Windows.Forms.Control.OnPaint%2A> for efficiency.</span></span>  
  
-   <span data-ttu-id="fc32e-111">.NET Framework 클래스 라이브러리는 정수, 10진수 숫자, 부울 값 등과 같은 일반적인 데이터 형식에 대해 형식 변환기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fc32e-111">The .NET Framework class library provides type converters for common data types such as integers, decimal numbers, Boolean values, and others.</span></span> <span data-ttu-id="fc32e-112">형식 변환기의 목적은 일반적으로 문자열을 값으로 변환하도록 제공합니다(문자열 데이터에서 다른 데이터 형식으로).</span><span class="sxs-lookup"><span data-stu-id="fc32e-112">The purpose of a type converter is generally to provide string-to-value conversion (from string data to other data types).</span></span> <span data-ttu-id="fc32e-113">일반적인 데이터 형식은 값을 문자열로 변환하고 문자열을 적절한 데이터 형식으로 변환하는 기본 형식 변환기와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc32e-113">Common data types are associated with default type converters that convert values into strings and strings into the appropriate data types.</span></span> <span data-ttu-id="fc32e-114">사용자 지정(즉, 비표준) 데이터 형식인 속성을 정의하는 경우 형식 변환기를 지정하는 특성을 적용하여 해당 속성과 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc32e-114">If you define a property that is a custom (that is, nonstandard) data type, you will have to apply an attribute that specifies the type converter to associate with that property.</span></span> <span data-ttu-id="fc32e-115">특성을 사용하여 사용자 지정 UI 형식 편집기를 속성과 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc32e-115">You can also use an attribute to associate a custom UI type editor with a property.</span></span> <span data-ttu-id="fc32e-116">UI 형식 편집기는 속성이나 데이터 형식을 편집하는 사용자 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fc32e-116">A UI type editor provides a user interface for editing a property or data type.</span></span> <span data-ttu-id="fc32e-117">색 선택은 UI 형식 편집기의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="fc32e-117">A color picker is an example of a UI type editor.</span></span> <span data-ttu-id="fc32e-118">이 항목의 끝에 특성의 예가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc32e-118">Examples of attributes are given at the end of this topic.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fc32e-119">사용자 지정 속성에 형식 변환기 또는 UI 형식 편집기를 사용할 수 없는 경우 [디자인 타임 지원 확장](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)에 설명된 대로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc32e-119">If a type converter or a UI type editor is not available for your custom property, you can implement one as described in [Extending Design-Time Support](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2).</span></span>  
  
 <span data-ttu-id="fc32e-120">다음 코드 조각은 사용자 지정 컨트롤 `FlashTrackBar`에 대해 `EndColor`이라는 사용자 지정 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fc32e-120">The following code fragment defines a custom property named `EndColor` for the custom control `FlashTrackBar`.</span></span>  
  
```vb  
Public Class FlashTrackBar  
   Inherits Control  
   ...  
   ' Private data member that backs the EndColor property.  
   Private _endColor As Color = Color.LimeGreen  
  
   ' The Category attribute tells the designer to display  
   ' it in the Flash grouping.   
   ' The Description attribute provides a description of  
   ' the property.   
   <Category("Flash"), _  
   Description("The ending color of the bar.")>  _  
   Public Property EndColor() As Color  
      ' The public property EndColor accesses _endColor.  
      Get  
         Return _endColor  
      End Get  
      Set  
         _endColor = value  
         If Not (baseBackground Is Nothing) And showGradient Then  
            baseBackground.Dispose()  
            baseBackground = Nothing  
         End If  
         ' The Invalidate method calls the OnPaint method, which redraws    
         ' the control.  
         Invalidate()  
      End Set  
   End Property  
   ...  
End Class  
```  
  
```csharp  
public class FlashTrackBar : Control {  
   ...  
   // Private data member that backs the EndColor property.  
   private Color endColor = Color.LimeGreen;  
   // The Category attribute tells the designer to display  
   // it in the Flash grouping.   
   // The Description attribute provides a description of  
   // the property.   
   [  
   Category("Flash"),  
   Description("The ending color of the bar.")  
   ]  
   // The public property EndColor accesses endColor.  
   public Color EndColor {  
      get {  
         return endColor;  
      }  
      set {  
         endColor = value;  
         if (baseBackground != null && showGradient) {  
            baseBackground.Dispose();  
            baseBackground = null;  
         }  
         // The Invalidate method calls the OnPaint method, which redraws   
         // the control.  
         Invalidate();  
      }  
   }  
   ...  
}  
```  
  
 <span data-ttu-id="fc32e-121">다음 코드 조각은 형식 변환기 및 UI 형식 편집기를 속성 `Value`과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="fc32e-121">The following code fragment associates a type converter and a UI type editor with the property `Value`.</span></span> <span data-ttu-id="fc32e-122">이 경우 `Value` 는 정수 이며 기본 형식 변환기가 있지만 <xref:System.ComponentModel.TypeConverterAttribute> 특성을 적용 한 사용자 지정 형식 변환기 (`FlashTrackBarValueConverter`)를 백분율로 표시 하려면 디자이너 수 있게 해 주는 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc32e-122">In this case `Value` is an integer and has a default type converter, but the <xref:System.ComponentModel.TypeConverterAttribute> attribute applies a custom type converter (`FlashTrackBarValueConverter`) that enables the designer to display it as a percentage.</span></span> <span data-ttu-id="fc32e-123">UI 형식 편집기인 `FlashTrackBarValueEditor`은 백분율을 시각적으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc32e-123">The UI type editor, `FlashTrackBarValueEditor`, allows the percentage to be displayed visually.</span></span> <span data-ttu-id="fc32e-124">또한 보여 주는이 예제는 형식 변환기 또는 편집기로 지정 된는 <xref:System.ComponentModel.TypeConverterAttribute> 또는 <xref:System.ComponentModel.EditorAttribute> 특성 기본 변환기를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc32e-124">This example also shows that the type converter or editor specified by the <xref:System.ComponentModel.TypeConverterAttribute> or <xref:System.ComponentModel.EditorAttribute> attribute overrides the default converter.</span></span>  
  
```vb  
<Category("Flash"), _  
TypeConverter(GetType(FlashTrackBarValueConverter)), _  
Editor(GetType(FlashTrackBarValueEditor), _  
GetType(UITypeEditor)), _  
Description("The current value of the track bar.  You can enter an actual value or a percentage.")>  _  
Public ReadOnly Property Value() As Integer  
...  
End Property  
```  
  
```csharp  
[  
Category("Flash"),   
TypeConverter(typeof(FlashTrackBarValueConverter)),  
Editor(typeof(FlashTrackBarValueEditor), typeof(UITypeEditor)),  
Description("The current value of the track bar.  You can enter an actual value or a percentage.")  
]  
public int Value {  
...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="fc32e-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc32e-125">See Also</span></span>  
 [<span data-ttu-id="fc32e-126">Windows Forms 컨트롤의 속성</span><span class="sxs-lookup"><span data-stu-id="fc32e-126">Properties in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 [<span data-ttu-id="fc32e-127">ShouldSerialize 및 Reset 메서드를 사용하여 기본값 정의</span><span class="sxs-lookup"><span data-stu-id="fc32e-127">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 [<span data-ttu-id="fc32e-128">속성 변경 이벤트</span><span class="sxs-lookup"><span data-stu-id="fc32e-128">Property-Changed Events</span></span>](../../../../docs/framework/winforms/controls/property-changed-events.md)  
 [<span data-ttu-id="fc32e-129">Windows Forms 컨트롤의 특성</span><span class="sxs-lookup"><span data-stu-id="fc32e-129">Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)
