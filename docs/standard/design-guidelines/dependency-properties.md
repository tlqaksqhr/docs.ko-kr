---
title: 종속성 속성
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e5ab558149615128f6d8cb0a68bf7f70e7006b79
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="dependency-properties"></a><span data-ttu-id="0243c-102">종속성 속성</span><span class="sxs-lookup"><span data-stu-id="0243c-102">Dependency Properties</span></span>
<span data-ttu-id="0243c-103">종속성 속성 DP ()은 예를 들어 유형 변수 (필드)를 저장 하는 대신 속성 저장소의 해당 값을 저장 하는 일반 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-103">A dependency property (DP) is a regular property that stores its value in a property store instead of storing it in a type variable (field), for example.</span></span>  
  
 <span data-ttu-id="0243c-104">연결 된 종속성 속성은 개체와 해당 컨테이너 간의 관계를 설명 하는 "속성"을 나타내는 정적 Get 및 Set 메서드로 모델링 되는 종속성 속성의 종류 (예: 위치는 `Button` 개체에 `Panel` 컨테이너)입니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-104">An attached dependency property is a kind of dependency property modeled as static Get and Set methods representing "properties" describing relationships between objects and their containers (e.g., the position of a `Button` object on a `Panel` container).</span></span>  
  
 <span data-ttu-id="0243c-105">**✓ 않습니다** 스타일 지정, 트리거, 데이터 바인딩, 애니메이션, 동적 리소스 상속 같은 WPF 기능을 지 원하는 속성을 사용 해야 할 경우 종속성 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-105">**✓ DO** provide the dependency properties, if you need the properties to support WPF features such as styling, triggers, data binding, animations, dynamic resources, and inheritance.</span></span>  
  
## <a name="dependency-property-design"></a><span data-ttu-id="0243c-106">종속성 속성 디자인</span><span class="sxs-lookup"><span data-stu-id="0243c-106">Dependency Property Design</span></span>  
 <span data-ttu-id="0243c-107">**✓ 않습니다** 에서 상속 <xref:System.Windows.DependencyObject>, 또는 종속성 속성을 구현 하는 경우 하위 유형 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-107">**✓ DO** inherit from <xref:System.Windows.DependencyObject>, or one of its subtypes, when implementing dependency properties.</span></span> <span data-ttu-id="0243c-108">형식을 효율적이 지 속성 저장소의 구현을 제공 하 고 자동으로 WPF 데이터 바인딩을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-108">The type provides a very efficient implementation of a property store and automatically supports WPF data binding.</span></span>  
  
 <span data-ttu-id="0243c-109">**✓ 않습니다** 일반 CLR 속성 및 인스턴스를 저장 합니다. 공용 정적 읽기 전용 필드를 제공 <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> 각 종속성 속성에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-109">**✓ DO** provide a regular CLR property and public static read-only field storing an instance of <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> for each dependency property.</span></span>  
  
 <span data-ttu-id="0243c-110">**✓ 않습니다** 인스턴스 메서드를 호출 하 여 종속성 속성을 구현 <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> 및 <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-110">**✓ DO** implement dependency properties by calling instance methods <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> and <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="0243c-111">**✓ 않습니다** "속성과" 속성의 이름을 접미사로 붙여 하 여 종속성 속성의 정적 필드의 이름을</span><span class="sxs-lookup"><span data-stu-id="0243c-111">**✓ DO** name the dependency property static field by suffixing the name of the property with "Property."</span></span>  
  
 <span data-ttu-id="0243c-112">**X 하지 않으면** 코드에서 종속성 속성의 기본값을 명시적으로 설정; 대신 메타 데이터에서 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-112">**X DO NOT** set default values of dependency properties explicitly in code; set them in metadata instead.</span></span>  
  
 <span data-ttu-id="0243c-113">속성이 기본값을 명시적으로 설정 하면 해당 속성은 스타일 지정과 같이 암시적 몇 가지 방법으로 설정 되지 하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-113">If you set a property default explicitly, you might prevent that property from being set by some implicit means, such as a styling.</span></span>  
  
 <span data-ttu-id="0243c-114">**X 하지 않으면** 정적 필드에 액세스 하는 표준 코드 이외의 속성 접근자에 코드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-114">**X DO NOT** put code in the property accessors other than the standard code to access the static field.</span></span>  
  
 <span data-ttu-id="0243c-115">정적 필드를 직접 사용 스타일을 지정 하기 때문에 속성을 설정 하는 스타일 지정과 같이 암시적 방법으로 코드 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-115">That code won’t execute if the property is set by implicit means, such as a styling, because styling uses the static field directly.</span></span>  
  
 <span data-ttu-id="0243c-116">**X 하지 않으면** 종속성 속성을 사용 하 여 보안 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-116">**X DO NOT** use dependency properties to store secure data.</span></span> <span data-ttu-id="0243c-117">심지어 사설 종속성 속성은 공개적으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-117">Even private dependency properties can be accessed publicly.</span></span>  
  
## <a name="attached-dependency-property-design"></a><span data-ttu-id="0243c-118">연결 된 종속성 속성 디자인</span><span class="sxs-lookup"><span data-stu-id="0243c-118">Attached Dependency Property Design</span></span>  
 <span data-ttu-id="0243c-119">이전 섹션에서 설명 하는 종속성 속성을의 선언 형식이; 내장 속성을 나타냅니다. 예를 들어는 `Text` 속성의 속성은 `TextButton`를 선언 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-119">Dependency properties described in the preceding section represent intrinsic properties of the declaring type; for example, the `Text` property is a property of `TextButton`, which declares it.</span></span> <span data-ttu-id="0243c-120">종속성 속성의 특별 한 종류에는 연결 된 종속성 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-120">A special kind of dependency property is the attached dependency property.</span></span>  
  
 <span data-ttu-id="0243c-121">연결된 된 속성의 좋은 예는 <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-121">A classic example of an attached property is the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="0243c-122">만 관련 되 고 "연결 되어" 단추를 모눈으로 단추를 표에 포함 되어 있으면 이지만 속성 단추 (하지 표의) 열의 위치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-122">The property represents Button’s (not Grid’s) column position, but it is only relevant if the Button is contained in a Grid, and so it's "attached" to Buttons by Grids.</span></span>  
  
```  
<Grid>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition />  
        <ColumnDefinition />  
    </Grid.ColumnDefinitions>  
  
    <Button Grid.Column="0">Click</Button>  
    <Button Grid.Column="1">Clack</Button>  
</Grid>  
```  
  
 <span data-ttu-id="0243c-123">연결된 된 속성의 정의 같습니다 대부분의 일반 종속성 속성을 제외 하 고 접근자 Get 및 Set 메서드를 정적으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-123">The definition of an attached property looks mostly like that of a regular dependency property, except that the accessors are represented by static Get and Set methods:</span></span>  
  
```  
public class Grid {  
  
    public static int GetColumn(DependencyObject obj) {  
        return (int)obj.GetValue(ColumnProperty);  
    }  
  
    public static void SetColumn(DependencyObject obj, int value) {  
        obj.SetValue(ColumnProperty,value);  
    }  
  
    public static readonly DependencyProperty ColumnProperty =  
        DependencyProperty.RegisterAttached(  
            "Column",  
            typeof(int),  
            typeof(Grid)  
    );  
}  
```  
  
## <a name="dependency-property-validation"></a><span data-ttu-id="0243c-124">종속성 속성의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="0243c-124">Dependency Property Validation</span></span>  
 <span data-ttu-id="0243c-125">속성은 종종 유효성 검사에 영향을 주는 섞어 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-125">Properties often implement what is called validation.</span></span> <span data-ttu-id="0243c-126">유효성 검사 논리에는 속성의 값을 변경 하려고 하면 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-126">Validation logic executes when an attempt is made to change the value of a property.</span></span>  
  
 <span data-ttu-id="0243c-127">그러나 종속성 속성 접근자는 임의의 유효성 검사 코드를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-127">Unfortunately dependency property accessors cannot contain arbitrary validation code.</span></span> <span data-ttu-id="0243c-128">대신, 속성 유효성 검사 논리를 종속성 속성을 등록할 때 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-128">Instead, dependency property validation logic needs to be specified during property registration.</span></span>  
  
 <span data-ttu-id="0243c-129">**X 하지 않으면** 속성의 접근자에 종속성 속성 유효성 검사 논리를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-129">**X DO NOT** put dependency property validation logic in the property’s accessors.</span></span> <span data-ttu-id="0243c-130">대신에 대 한 유효성 검사 콜백을 전달 `DependencyProperty.Register` 메서드.</span><span class="sxs-lookup"><span data-stu-id="0243c-130">Instead, pass a validation callback to `DependencyProperty.Register` method.</span></span>  
  
## <a name="dependency-property-change-notifications"></a><span data-ttu-id="0243c-131">종속성 속성 변경 알림</span><span class="sxs-lookup"><span data-stu-id="0243c-131">Dependency Property Change Notifications</span></span>  
 <span data-ttu-id="0243c-132">**X 하지 않으면** 종속성 속성 접근자의 변경 알림 논리를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-132">**X DO NOT** implement change notification logic in dependency property accessors.</span></span> <span data-ttu-id="0243c-133">종속성 속성에 대 한 변경 알림 콜백을 제공 하 여 사용 해야 하는 기본 제공 변경 알림 기능에는 <xref:System.Windows.PropertyMetadata>합니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-133">Dependency properties have a built-in change notifications feature that must be used by supplying a change notification callback to the <xref:System.Windows.PropertyMetadata>.</span></span>  
  
## <a name="dependency-property-value-coercion"></a><span data-ttu-id="0243c-134">종속성 속성 값 강제 변환</span><span class="sxs-lookup"><span data-stu-id="0243c-134">Dependency Property Value Coercion</span></span>  
 <span data-ttu-id="0243c-135">속성 강제 변환 속성 저장소를 실제로 수정 하기 전에 속성 setter에 제공 된 값이 setter에서 수정 될 때 수행이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-135">Property coercion takes place when the value given to a property setter is modified by the setter before the property store is actually modified.</span></span>  
  
 <span data-ttu-id="0243c-136">**X 하지 않으면** 종속성 속성 접근자에서 강제 변환 논리를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-136">**X DO NOT** implement coercion logic in dependency property accessors.</span></span>  
  
 <span data-ttu-id="0243c-137">종속성 속성 기능이 기본 제공 강제 변환 및 강제 변환 콜백을 제공 하 여 사용할 수 있습니다는 `PropertyMetadata`합니다.</span><span class="sxs-lookup"><span data-stu-id="0243c-137">Dependency properties have a built-in coercion feature, and it can be used by supplying a coercion callback to the `PropertyMetadata`.</span></span>  
  
 <span data-ttu-id="0243c-138">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="0243c-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="0243c-139">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="0243c-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0243c-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0243c-140">See Also</span></span>  
 [<span data-ttu-id="0243c-141">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="0243c-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="0243c-142">일반 디자인 패턴</span><span class="sxs-lookup"><span data-stu-id="0243c-142">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)
