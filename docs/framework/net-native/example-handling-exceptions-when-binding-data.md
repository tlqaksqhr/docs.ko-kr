---
title: "예: 데이터를 바인딩하는 경우 예외 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd63ed96-9853-46dc-ade5-7bd1b0f39110
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e2714d53426bfee22b3d83d76b766816d9bc9d60
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="example-handling-exceptions-when-binding-data"></a><span data-ttu-id="6fff8-102">예: 데이터를 바인딩하는 경우 예외 처리</span><span class="sxs-lookup"><span data-stu-id="6fff8-102">Example: Handling Exceptions When Binding Data</span></span>
> [!NOTE]
>  <span data-ttu-id="6fff8-103">이 항목은 시험판 소프트웨어인 .NET Native Developer Preview를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="6fff8-103">This topic refers to the .NET Native Developer Preview, which is pre-release software.</span></span> <span data-ttu-id="6fff8-104">이 Preview 버전은 [Microsoft Connect 웹 사이트](http://go.microsoft.com/fwlink/?LinkId=394611)에서 다운로드할 수 있습니다(등록 필요).</span><span class="sxs-lookup"><span data-stu-id="6fff8-104">You can download the preview from the [Microsoft Connect website](http://go.microsoft.com/fwlink/?LinkId=394611) (requires registration).</span></span>  
  
 <span data-ttu-id="6fff8-105">다음 예제에서는 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 도구 체인을 사용하여 컴파일한 앱이 데이터 바인딩을 시도하면 throw되는 [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) 예외를 해결하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6fff8-105">The following example shows how to resolve a [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) exception that is thrown when an app compiled with the [!INCLUDE[net_native](../../../includes/net-native-md.md)] tool chain tries to bind data.</span></span> <span data-ttu-id="6fff8-106">예외 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6fff8-106">Here’s the exception information:</span></span>  
  
```  
This operation cannot be carried out as metadata for the following type was removed for performance reasons:   
App.ViewModels.MainPageVM  
```  
  
 <span data-ttu-id="6fff8-107">관련 호출 스택은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6fff8-107">Here's the associated call stack:</span></span>  
  
```  
Reflection::Execution::ReflectionDomainSetupImplementation.CreateNonInvokabilityException+0x238  
Reflection::Core::ReflectionDomain.CreateNonInvokabilityException+0x2e  
Reflection::Core::Execution::ExecutionEnvironment.+0x316  
System::Reflection::Runtime::PropertyInfos::RuntimePropertyInfo.GetValue+0x1cb  
System::Reflection::PropertyInfo.GetValue+0x22  
System::Runtime::InteropServices::WindowsRuntime::CustomPropertyImpl.GetValue+0x42  
App!$66_Interop::McgNative.Func_IInspectable_IInspectable+0x158  
App!$66_Interop::McgNative::__vtable_Windows_UI_Xaml_Data__ICustomProperty.GetValue__STUB+0x46  
Windows_UI_Xaml!DirectUI::PropertyProviderPropertyAccess::GetValue+0x3f   
Windows_UI_Xaml!DirectUI::PropertyAccessPathStep::GetValue+0x31   
Windows_UI_Xaml!DirectUI::PropertyPathListener::ConnectPathStep+0x113  
```  
  
## <a name="what-was-the-app-doing"></a><span data-ttu-id="6fff8-108">앱이 수행 중이었던 작업</span><span class="sxs-lookup"><span data-stu-id="6fff8-108">What was the app doing?</span></span>  
 <span data-ttu-id="6fff8-109">스택 베이스에서 [Windows.UI.Xaml](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.aspx) 네임스페이스의 프레임은 XAML 렌더링 엔진이 실행 중이었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6fff8-109">At the base of the stack, frames from the [Windows.UI.Xaml](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.aspx) namespace indicate that the XAML rendering engine was running.</span></span>   <span data-ttu-id="6fff8-110">또한 <xref:System.Reflection.PropertyInfo.GetValue%2A?displayProperty=nameWithType> 메서드가 사용되었으므로 해당 메타데이터가 제거된 형식에 대해 속성 값의 리플렉션 기반 조회를 수행했음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fff8-110">The use of the <xref:System.Reflection.PropertyInfo.GetValue%2A?displayProperty=nameWithType> method indicates a reflection-based lookup of a property’s value on the type whose metadata was removed.</span></span>  
  
 <span data-ttu-id="6fff8-111">메타데이터 지시문을 제공하는 첫 단계에서는 모든 속성에 액세스할 수 있도록 형식에 대해 `serialize` 메타데이터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6fff8-111">The first step in providing a metadata directive would be to add `serialize` metadata for the type so that its properties are all accessible:</span></span>  
  
```xml  
<Type Name="App.ViewModels.MainPageVM" Serialize="Required Public" />  
```  
  
## <a name="is-this-an-isolated-case"></a><span data-ttu-id="6fff8-112">사례의 격리 여부 확인</span><span class="sxs-lookup"><span data-stu-id="6fff8-112">Is this an isolated case?</span></span>  
 <span data-ttu-id="6fff8-113">이 시나리오에서는 데이터 바인딩에서 `ViewModel` 하나의 메타데이터가 불완전하면 나머지 항목의 메타데이터도 불완전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fff8-113">In this scenario, if data binding has incomplete metadata for one `ViewModel`, it may for others, too.</span></span>  <span data-ttu-id="6fff8-114">앱의 뷰 모델이 모두 `App.ViewModels` 네임스페이스에 포함되는 방식으로 코드를 작성한 경우에는 보다 일반적인 런타임 지시문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fff8-114">If the code is structured in a way that the app’s view models are all in the `App.ViewModels` namespace, you could use a more general runtime directive:</span></span>  
  
```xml  
<Namespace Name="App.ViewModels " Serialize="Required Public" />  
```  
  
## <a name="could-the-code-be-rewritten-to-not-use-reflection"></a><span data-ttu-id="6fff8-115">리플렉션을 사용하지 않도록 코드 다시 작성 가능 여부 확인</span><span class="sxs-lookup"><span data-stu-id="6fff8-115">Could the code be rewritten to not use reflection?</span></span>  
 <span data-ttu-id="6fff8-116">데이터 바인딩에서는 리플렉션을 많이 사용하므로 리플렉션을 사용하지 않도록 코드를 변경하기는 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="6fff8-116">Because data binding is reflection-intensive, changing the code to avoid reflection isn’t feasible.</span></span>  
  
 <span data-ttu-id="6fff8-117">그러나 `ViewModel`을 XAML 페이지로 지정하여 도구 체인이 컴파일 타임에 속성 바인딩을 올바른 형식과 연결하고, 런타임 지시문을 사용하지 않고 메타데이터를 유지하도록 할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fff8-117">However, there are ways to specify the `ViewModel` to the XAML page so that the tool chain can associate property bindings with the correct type at compile time and keep the metadata without using a runtime directive.</span></span>  <span data-ttu-id="6fff8-118">예를 들어 속성에 대해 [Windows.UI.Xaml.Data.BindableAttribute](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.data.bindableattribute.aspx) 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fff8-118">For example, you could apply the [Windows.UI.Xaml.Data.BindableAttribute](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.data.bindableattribute.aspx) attribute on properties.</span></span> <span data-ttu-id="6fff8-119">이렇게 하면 XAML 컴파일러가 필요한 조회 정보를 생성하고 Default.rd.xml 파일에서 런타임 지시문이 필요하도록 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fff8-119">This causes the XAML compiler to generate the required lookup information and avoids requiring a runtime directive in the Default.rd.xml file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fff8-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6fff8-120">See Also</span></span>  
 [<span data-ttu-id="6fff8-121">시작</span><span class="sxs-lookup"><span data-stu-id="6fff8-121">Getting Started</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
 [<span data-ttu-id="6fff8-122">예: 동적 프로그래밍 문제 해결</span><span class="sxs-lookup"><span data-stu-id="6fff8-122">Example: Troubleshooting Dynamic Programming</span></span>](../../../docs/framework/net-native/example-troubleshooting-dynamic-programming.md)
