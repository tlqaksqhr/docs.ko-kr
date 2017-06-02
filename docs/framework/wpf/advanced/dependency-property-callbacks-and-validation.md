---
title: "종속성 속성 콜백 및 유효성 검사 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "콜백, 유효성 검사"
  - "강제 값 콜백"
  - "종속성 속성, 콜백"
  - "종속성 속성, 유효성 검사"
  - "종속성 속성 유효성 검사"
ms.assetid: 48db5fb2-da7f-49a6-8e81-3540e7b25825
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 종속성 속성 콜백 및 유효성 검사
이 항목에서는 유효성 검사 확인, 속성의 유효 값이 변경될 때마다 호출되는 콜백, 값 확인 시 발생할 수 있는 외부 영향 재정의 등 속성 관련 기능을 위한 대체 사용자 지정 구현을 사용하여 종속성 속성을 만드는 방법에 대해 설명합니다.  또한 이러한 기법을 사용하여 기본 속성 시스템 동작을 확장하는 것이 적절한 시나리오에 대해서도 설명합니다.  
  
   
  
<a name="prerequisites"></a>   
## 사전 요구 사항  
 이 항목에서는 사용자가 종속성 속성을 구현하는 기본 시나리오와 사용자 지정 종속성 속성에 메타데이터를 적용하는 방법에 대해 잘 알고 있다고 가정합니다.  자세한 내용은 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md) 및 [종속성 속성 메타데이터](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)를 참조하십시오.  
  
<a name="Validation_Callbacks"></a>   
## 유효성 검사 콜백  
 유효성 검사 콜백은 처음 등록할 때 종속성 속성에 할당할 수 있습니다.  유효성 검사 콜백은 속성 메타데이터의 일부가 아니며, <xref:System.Windows.DependencyProperty.Register%2A> 메서드의 직접 입력입니다.  따라서 종속성 속성에 대한 유효성 검사 콜백을 만든 후에는 새 구현으로 재정의할 수 없습니다.  
  
 [!code-csharp[DPCallbackOverride#CurrentDefinitionWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#currentdefinitionwithwrapper)]
 [!code-vb[DPCallbackOverride#CurrentDefinitionWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#currentdefinitionwithwrapper)]  
  
 콜백은 개체 값을 제공하는 방식으로 구현되며,  제공된 값이 속성에 적합한 경우에는 `true`를 반환하고 적합하지 않은 경우에는 `false`를 반환합니다.  여기에서는 속성이 속성 시스템에 등록된 올바른 형식이라고 가정하므로 일반적으로 콜백 내에서 형식 확인이 수행되지 않습니다.  콜백은 속성 시스템에 의해 다양한 작업에 사용됩니다.  이러한 작업에는 기본값에 의한 초기 형식 초기화, <xref:System.Windows.DependencyObject.SetValue%2A> 호출을 통한 프로그래밍 방식의 변경, 제공된 새 기본값으로 메타데이터를 재정의하는 작업 등이 포함됩니다.  이러한 작업 중 하나에서 유효성 검사 콜백이 호출되고 `false`가 반환되는 경우 예외가 발생됩니다.  응용 프로그램 작성자는 이러한 예외를 처리해야 합니다.  유효성 검사 콜백의 일반적인 용도는 열거형 값의 유효성을 검사하는 것이거나 속성이 0 이상이 되어야 하는 측정값을 설정할 때 integer 또는 double 값을 제약하는 것입니다.  
  
 유효성 검사 콜백은 인스턴스 유효성 검사기가 아니라 클래스 유효성 검사기로 사용됩니다.  콜백 매개 변수는 유효성을 검사할 속성이 설정되어 있는 특정 <xref:System.Windows.DependencyObject>를 전달하지 않습니다.  따라서 인스턴스별 속성 값이 다른 속성의 인스턴스별 값 또는 런타임 같은 요소에 종속되는 경우처럼 속성 값에 영향을 줄 가능성이 있는 "종속성"을 적용할 때는 유효성 검사 콜백이 유용하지 않습니다.  
  
 다음은 매우 간단한 유효성 검사 콜백 시나리오에 대한 예제 코드로서, 유효성 검사를 통해 <xref:System.Double> 기본 형식으로 형식화된 속성이 <xref:System.Double.PositiveInfinity> 또는 <xref:System.Double.NegativeInfinity>가 아닌지 확인하는 것입니다.  
  
 [!code-csharp[DPCallbackOverride#ValidateValueCallback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#validatevaluecallback)]
 [!code-vb[DPCallbackOverride#ValidateValueCallback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#validatevaluecallback)]  
  
<a name="Coerce_Value_Callbacks_and_Property_Changed_Events"></a>   
## 강제 값 콜백 및 속성 변경 이벤트  
 강제 값 콜백은 종속성 속성 값이 변경될 때마다 속성 시스템에서 호출되는 <xref:System.Windows.PropertyChangedCallback> 구현과 마찬가지로 속성에 대한 특정 <xref:System.Windows.DependencyObject> 인스턴스를 전달합니다.  이 두 콜백을 조합하여 사용하면 한 속성의 변경 내용이 다른 속성의 강제 변환이나 재계산을 유발하는 일련의 속성을 만들 수 있습니다.  
  
 종속성 속성 연결을 사용하는 일반적인 시나리오는 요소가 최소값과 최대값에 대해 하나씩 값을 유지하고 실제 값이나 현재 값에 대한 세 번째 속성을 유지하는 사용자 인터페이스 기반 속성을 사용할 때입니다.  따라서 현재 값이 새 최대값을 초과할 때 최대값을 조정하려는 경우 현재 값을 강제로 새로운 최대값보다 크지 않게 만들 수 있습니다. 유사한 관계가 최소값과 현재 값에도 적용됩니다.  
  
 다음은 이 관계를 설명하는 세 가지 종속성 속성 중 하나에 대한 매우 간략한 예제 코드입니다.  이 예제에서는 관련 \*Reading 속성의 Min\/Max\/Current 집합에 대한 `CurrentReading` 속성을 등록하는 방법을 보여 줍니다.  여기에는 이전 단원에서 설명한 유효성 검사가 사용됩니다.  
  
 [!code-csharp[DPCallbackOverride#CurrentDefinitionWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#currentdefinitionwithwrapper)]
 [!code-vb[DPCallbackOverride#CurrentDefinitionWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#currentdefinitionwithwrapper)]  
  
 Current에 대한 속성 변경 콜백은 다른 속성에 등록된 강제 값 콜백을 명시적으로 호출하여 변경 내용을 해당 종속 속성에 전달하는 데 사용됩니다.  
  
 [!code-csharp[DPCallbackOverride#OnPCCurrent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#onpccurrent)]
 [!code-vb[DPCallbackOverride#OnPCCurrent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#onpccurrent)]  
  
 강제 값 콜백은 현재 속성이 종속될 수 있는 속성 값을 확인하여 필요한 경우 현재 값을 강제로 변환합니다.  
  
 [!code-csharp[DPCallbackOverride#CoerceCurrent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#coercecurrent)]
 [!code-vb[DPCallbackOverride#CoerceCurrent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#coercecurrent)]  
  
> [!NOTE]
>  속성 기본값은 강제로 변환되지 않습니다.  속성 값이 초기 기본값을 가지고 있거나 <xref:System.Windows.DependencyObject.ClearValue%2A>를 사용하여 다른 값을 지우는 경우에 기본값과 동일한 속성 값이 설정될 수 있습니다.  
  
 강제 값 및 속성 변경 콜백은 속성 메타데이터의 일부입니다.  따라서 형식의 속성에 대한 메타데이터를 재정의하면 종속성 속성을 소유하는 형식에서 파생시킨 형식에 존재하는 것처럼 특정 종속성 속성에 대한 콜백을 변경할 수 있습니다.  
  
<a name="Advanced"></a>   
## 고급 강제 변환 및 콜백 시나리오  
  
### 제약 조건 및 원하는 값  
 사용자가 선언한 논리에 따라 값을 강제로 변환하지만 로컬에서 설정된 속성의 강제 변환된 값이 내부적으로 "원하는 값"을 계속 유지하게 만들기 위해 속성 시스템에서 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 콜백이 사용됩니다.  제약 조건이 응용 프로그램 수명 동안 동적으로 변경될 수 있는 다른 속성 값에 기반하는 경우 강제 제약 조건 또한 동적으로 변경되며 제약 조건이 적용된 속성은 지정된 새 제약 조건에서 가능한 원하는 값과 가까운 값으로 해당 값을 변경할 수 있습니다.  모든 제약 조건이 리프트되면 값이 원하는 값이 됩니다.  순환하는 방식으로 다른 속성에 종속되는 여러 개의 속성이 있는 경우에는 다소 복잡한 종속성 시나리오를 도입할 수 있습니다.  예를 들어 Min\/Max\/Current 시나리오에서 Minimum 및 Maximum을 사용자가 설정할 수 있게 만들 수 있습니다.  그렇게 하는 경우 Maximum이 항상 Minimum보다 크게 만들고 Minimum이 항상 Maximum보다 작게 만들어야 합니다.  하지만 이러한 강제 변환이 활성화되고 Maximum이 Minimum으로 강제 변환되는 경우에는 Current가 두 값에 모두 종속되고 두 값의 사이 값인 범위\(0\)로 제한되므로 값을 설정할 수 없는 상태가 됩니다.  이 경우 Current의 원하는 값이 저장되어 있고 제약 조건이 느슨할 때 원하는 값에 도달하려고 하기 때문에 Maximum 또는 Minimum이 조정되면 Current가 두 값 중 하나를 "따르는" 것처럼 보이게 됩니다.  
  
 복잡한 종속성에 기술적인 문제는 전혀 없지만 많은 수의 재계산이 필요한 경우에는 성능에 나쁜 영향을 줄 수 있고 UI에 직접 적용되는 경우에는 사용자에게 혼란을 줄 수 있습니다.  속성 변경 값과 강제 값 콜백을 사용할 때에는 주의해야 하며 강제 변환을 시도할 때에는 가능한 한 모호하지 않게 처리하고 "과도한 제약"을 하지 않도록 해야 합니다.  
  
### CoerceValue를 사용하여 값 변경 취소  
 속성 시스템에서는 <xref:System.Windows.DependencyProperty.UnsetValue> 값을 반환하는 모든 <xref:System.Windows.CoerceValueCallback>을 특별하게 취급합니다.  특별하다고 하는 이유는 호출되는 <xref:System.Windows.CoerceValueCallback>에서 반환되는 속성 변경을 속성 시스템에서 거부하고 대신 속성의 이전 값을 보고하기 때문입니다.  비동기적으로 초기화된 속성 변경이 현재 개체 상태에 유효한지 확인하여 유효하지 않은 경우 변경을 억제하는 경우에 이 메커니즘이 유용합니다.  다른 가능한 시나리오는 속성 값 확인 구성 요소 중에서 보고된 값과 관련된 구성 요소에 따라 선택적으로 값을 억제하는 것입니다.  이렇게 하려면 콜백 및 속성 식별자에서 <xref:System.Windows.DependencyPropertyHelper.GetValueSource%2A>에 대한 입력으로 전달된 <xref:System.Windows.DependencyProperty>를 사용하여 <xref:System.Windows.ValueSource>를 처리합니다.  
  
## 참고 항목  
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [종속성 속성 메타데이터](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)   
 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)