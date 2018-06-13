---
title: 속성(F#)
description: 'F # 속성을 개체에 연결 된 값을 나타내는 멤버에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 7aa71b1801b44fedcb420b824078004c6c240dc2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566162"
---
# <a name="properties"></a><span data-ttu-id="3566e-103">속성</span><span class="sxs-lookup"><span data-stu-id="3566e-103">Properties</span></span>

<span data-ttu-id="3566e-104">*속성* 은 개체와 관련 된 값을 나타내는 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-104">*Properties* are members that represent values associated with an object.</span></span>


## <a name="syntax"></a><span data-ttu-id="3566e-105">구문</span><span class="sxs-lookup"><span data-stu-id="3566e-105">Syntax</span></span>

```fsharp
// Property that has both get and set defined.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with [accessibility-modifier] get() =
    get-function-body
and [accessibility-modifier] set parameter =
    set-function-body

// Alternative syntax for a property that has get and set.
[ attributes-for-get ]
[ static ] member [accessibility-modifier-for-get] [self-identifier.]PropertyName =
    get-function-body
[ attributes-for-set ]
[ static ] member [accessibility-modifier-for-set] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName =
    get-function-body

// Alternative syntax for property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with get() =
    get-function-body

// Property that has set only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Automatically implemented properties.
[ attributes ]
[ static ] member val [accessibility-modifier] PropertyName = initialization-expression [ with get, set ]
```

## <a name="remarks"></a><span data-ttu-id="3566e-106">설명</span><span class="sxs-lookup"><span data-stu-id="3566e-106">Remarks</span></span>
<span data-ttu-id="3566e-107">속성이 나타내는 "에" 또는 연결 되어 있는 개체 인스턴스를 해당 형식과 정적 속성에 대 한 데이터를 나타내는 개체 지향 프로그래밍에서 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-107">Properties represent the "has a" relationship in object-oriented programming, representing data that is associated with object instances or, for static properties, with the type.</span></span>

<span data-ttu-id="3566e-108">속성에 대 한 기본 값 (백업 저장소 라고도 함)을 명시적으로 지정 하려는 또는 컴파일러의 백업 저장소를 자동으로 생성 하도록 허용 하려는 경우에 따라 두 가지 방법으로 속성을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-108">You can declare properties in two ways, depending on whether you want to explicitly specify the underlying value (also called the backing store) for the property, or if you want to allow the compiler to automatically generate the backing store for you.</span></span> <span data-ttu-id="3566e-109">일반적으로 속성을 값 또는 변수에 대 한 간단한 래퍼에 자동으로 방법 및 속성에 특수 구현 하는 경우 명시적 방법의 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-109">Generally, you should use the more explicit way if the property has a non-trivial implementation and the automatic way when the property is just a simple wrapper for a value or variable.</span></span> <span data-ttu-id="3566e-110">사용 하 여 속성을 명시적으로 선언 하는 `member` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-110">To declare a property explicitly, use the `member` keyword.</span></span> <span data-ttu-id="3566e-111">이 선언 구문을 지정 하는 구문을 사용 하 여 다음의 `get` 및 `set` 라고도 메서드 *접근자*합니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-111">This declarative syntax is followed by the syntax that specifies the `get` and `set` methods, also named *accessors*.</span></span> <span data-ttu-id="3566e-112">다양 한 형태의 구문 섹션에 표시 된 명시적 구문 읽기/쓰기, 읽기 전용 및 쓰기 전용 속성에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-112">The various forms of the explicit syntax shown in the syntax section are used for read/write, read-only, and write-only properties.</span></span> <span data-ttu-id="3566e-113">읽기 전용 속성에 대 한 정의는 `get` 메서드; 쓰기 전용 속성에 대 한 정의는 `set` 메서드.</span><span class="sxs-lookup"><span data-stu-id="3566e-113">For read-only properties, you define only a `get` method; for write-only properties, define only a `set` method.</span></span> <span data-ttu-id="3566e-114">속성에 모두 때 `get` 및 `set` 접근자는 대체 구문을 사용 하 여 특성 및 다음 코드에 표시 된 대로 각 접근자에 대 한 다른 액세스 가능성 한정자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-114">Note that when a property has both `get` and `set` accessors, the alternative syntax enables you to specify attributes and accessibility modifiers that are different for each accessor, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

<span data-ttu-id="3566e-115">둘 다를 포함 하는 읽기/쓰기 속성에 대 한 한 `get` 및 `set` 메서드, 순서 `get` 및 `set` 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-115">For read/write properties, which have both a `get` and `set` method, the order of `get` and `set` can be reversed.</span></span> <span data-ttu-id="3566e-116">또는 표시 된 구문의 제공할 수 `get` 만 및에 대 한 표시 된 구문은 `set` 결합 된 구문을 사용 하는 대신만 합니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-116">Alternatively, you can provide the syntax shown for `get` only and the syntax shown for `set` only instead of using the combined syntax.</span></span> <span data-ttu-id="3566e-117">이 작업을 수행 하기가 개별 주석 `get` 또는 `set` 메서드를 리 만들어야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-117">Doing this makes it easier to comment out the individual `get` or `set` method, if that is something you might need to do.</span></span> <span data-ttu-id="3566e-118">이 대체 결합 된 구문을 사용 하 여 다음 코드에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-118">This alternative to using the combined syntax is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

<span data-ttu-id="3566e-119">개인 값 속성에 대 한 데이터 라고 하는 해당 보류 *백업 저장소*합니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-119">Private values that hold the data for properties are called *backing stores*.</span></span> <span data-ttu-id="3566e-120">백업 저장소를 자동으로 만드는 컴파일러를 사용 하 여 키워드 `member val`를 자체 식별자를 생략 한 다음 속성을 초기화 하는 식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-120">To have the compiler create the backing store automatically, use the keywords `member val`, omit the self-identifier, then provide an expression to initialize the property.</span></span> <span data-ttu-id="3566e-121">속성이 mutable로 이면 포함 `with get, set`합니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-121">If the property is to be mutable, include `with get, set`.</span></span> <span data-ttu-id="3566e-122">예를 들어 다음 클래스 형식에는 두 개의 자동으로 구현 된 속성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-122">For example, the following class type includes two automatically implemented properties.</span></span> <span data-ttu-id="3566e-123">`Property1` 읽기 전용 이므로 기본 생성자에 제공 되는 인수를 초기화 및 `Property2` 는 설정 가능한 속성을 빈 문자열로 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-123">`Property1` is read-only and is initialized to the argument provided to the primary constructor, and `Property2` is a settable property initialized to an empty string:</span></span>

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

<span data-ttu-id="3566e-124">자동으로 구현 된 속성은 형식 초기화 하는 일부 다른 멤버 정의 하기 전에 동일 하 게 포함 되어야 하므로 `let` 바인딩 및 `do` 형식 정의의 바인딩.</span><span class="sxs-lookup"><span data-stu-id="3566e-124">Automatically implemented properties are part of the initialization of a type, so they must be included before any other member definitions, just like `let` bindings and `do` bindings in a type definition.</span></span> <span data-ttu-id="3566e-125">Note 초기화 될 및 속성에 액세스할 때마다 하지 자동으로 구현 된 속성을 초기화 하는 식만 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-125">Note that the expression that initializes an automatically implemented property is only evaluated upon initialization, and not every time the property is accessed.</span></span> <span data-ttu-id="3566e-126">이 동작은 달리 명시적으로 구현 된 속성의 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-126">This behavior is in contrast to the behavior of an explicitly implemented property.</span></span> <span data-ttu-id="3566e-127">클래스의 생성자에 효과적으로 즉는 이러한 속성을 초기화 하는 코드가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-127">What this effectively means is that the code to initialize these properties is added to the constructor of a class.</span></span> <span data-ttu-id="3566e-128">이러한 차이 보여 주는 다음 코드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="3566e-128">Consider the following code that shows this difference:</span></span>

```fsharp
type MyClass() =
    let random  = new System.Random()
    member val AutoProperty = random.Next() with get, set
    member this.ExplicitProperty = random.Next()

let class1 = new MyClass()

printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
```

<span data-ttu-id="3566e-129">**출력**</span><span class="sxs-lookup"><span data-stu-id="3566e-129">**Output**</span></span>

```
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

<span data-ttu-id="3566e-130">앞의 코드 출력 AutoProperty 값 변경 된 때 아님을 반복적으로 호출는 ExplicitProperty가 호출 될 때마다 변경 하는 반면 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-130">The output of the preceding code shows that the value of AutoProperty is unchanged when called repeatedly, whereas the ExplicitProperty changes each time it is called.</span></span> <span data-ttu-id="3566e-131">명시적 속성에 대 한 getter 메서드가 있는 그대로 자동으로 구현 된 속성에 대 한 식을 계산 될 때마다 하지 않는다는 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-131">This demonstrates that the expression for an automatically implemented property is not evaluated each time, as is the getter method for the explicit property.</span></span>


>[!WARNING]
<span data-ttu-id="3566e-132">Entity Framework와 같은 일부 라이브러리는 (`System.Data.Entity`) 자동으로 구현 된 속성의 초기화와 잘 작동 하지 않는 기본 클래스 생성자에서 사용자 지정 작업을 수행 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-132">There are some libraries, such as the Entity Framework (`System.Data.Entity`) that perform custom operations in base class constructors that don't work well with the initialization of automatically implemented properties.</span></span> <span data-ttu-id="3566e-133">이 경우 명시적 속성을 사용 하 여 보십시오.</span><span class="sxs-lookup"><span data-stu-id="3566e-133">In those cases, try using explicit properties.</span></span>

<span data-ttu-id="3566e-134">속성은 클래스, 구조체, 구분 된 공용 구조체, 레코드, 인터페이스 및 형식 확장의 멤버일 수 및 개체 식에 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-134">Properties can be members of classes, structures, discriminated unions, records, interfaces, and type extensions and can also be defined in object expressions.</span></span>

<span data-ttu-id="3566e-135">특성 속성에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-135">Attributes can be applied to properties.</span></span> <span data-ttu-id="3566e-136">특성 속성에 적용할 특성 속성 앞에 있는 별도 줄에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-136">To apply an attribute to a property, write the attribute on a separate line before the property.</span></span> <span data-ttu-id="3566e-137">자세한 내용은 [특성](../attributes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3566e-137">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="3566e-138">기본적으로이 속성은 public입니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-138">By default, properties are public.</span></span> <span data-ttu-id="3566e-139">액세스 가능성 한정자 속성에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-139">Accessibility modifiers can also be applied to properties.</span></span> <span data-ttu-id="3566e-140">액세스 가능성 한정자를 적용 하려면 앞에 추가 즉시 속성의 이름을 둘 다에 적용 하려는 경우는 `get` 및 `set` 메서드를 추가 하기 전에 `get` 및 `set` 서로 다른 접근성이 키워드 각 접근자에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-140">To apply an accessibility modifier, add it immediately before the name of the property if it is meant to apply to both the `get` and `set` methods; add it before the `get` and `set` keywords if different accessibility is required for each accessor.</span></span> <span data-ttu-id="3566e-141">*접근성 한정자* 다음 중 하나일 수 있습니다: `public`, `private`, `internal`합니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-141">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="3566e-142">자세한 내용은 [액세스 제어](../access-control.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3566e-142">For more information, see [Access Control](../access-control.md).</span></span>

<span data-ttu-id="3566e-143">속성 구현이 속성에 액세스할 때마다 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-143">Property implementations are executed each time a property is accessed.</span></span>


## <a name="static-and-instance-properties"></a><span data-ttu-id="3566e-144">정적 및 인스턴스 속성</span><span class="sxs-lookup"><span data-stu-id="3566e-144">Static and Instance Properties</span></span>
<span data-ttu-id="3566e-145">속성은 인스턴스 속성 또는 정적 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-145">Properties can be static or instance properties.</span></span> <span data-ttu-id="3566e-146">정적 속성 인스턴스 없이 호출 될 수 있으며 개별 개체가 아니라는 형식과 연관 된 값에 대 한 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-146">Static properties can be invoked without an instance and are used for values associated with the type, not with individual objects.</span></span> <span data-ttu-id="3566e-147">정적 속성에 대 한 자체 식별자를 생략 합니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-147">For static properties, omit the self-identifier.</span></span> <span data-ttu-id="3566e-148">자체 식별자는 인스턴스 속성에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-148">The self-identifier is required for instance properties.</span></span>

<span data-ttu-id="3566e-149">정적 필드에 시나리오를 기반으로 하는 다음과 같은 정적 속성 정의가 `myStaticValue` 속성에 대 한 백업 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-149">The following static property definition is based on a scenario in which you have a static field `myStaticValue` that is the backing store for the property.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

<span data-ttu-id="3566e-150">속성 또한 수 배열 형식의 호출 되는 경우 *인덱싱된 속성*합니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-150">Properties can also be array-like, in which case they are called *indexed properties*.</span></span> <span data-ttu-id="3566e-151">자세한 내용은 참조 [인덱싱된 속성](indexed-properties.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-151">For more information, see [Indexed Properties](indexed-properties.md).</span></span>


## <a name="type-annotation-for-properties"></a><span data-ttu-id="3566e-152">속성에 대 한 형식 주석</span><span class="sxs-lookup"><span data-stu-id="3566e-152">Type Annotation for Properties</span></span>
<span data-ttu-id="3566e-153">대부분의 경우에서 컴파일러에서 백업 저장소의 형식에서 속성의 형식을 유추 하도록 충분 한 정보가 있지만 형식 주석을 추가 하 여 형식을 명시적으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-153">In many cases, the compiler has enough information to infer the type of a property from the type of the backing store, but you can set the type explicitly by adding a type annotation.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a><span data-ttu-id="3566e-154">Set 접근자 속성을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="3566e-154">Using Property set Accessors</span></span>
<span data-ttu-id="3566e-155">제공 하는 속성을 설정할 수 `set` 를 사용 하 여 접근자는 `<-` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-155">You can set properties that provide `set` accessors by using the `<-` operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

<span data-ttu-id="3566e-156">출력은 **20**합니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-156">The output is **20**.</span></span>


## <a name="abstract-properties"></a><span data-ttu-id="3566e-157">추상 속성</span><span class="sxs-lookup"><span data-stu-id="3566e-157">Abstract Properties</span></span>
<span data-ttu-id="3566e-158">속성은 abstract 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-158">Properties can be abstract.</span></span> <span data-ttu-id="3566e-159">메서드의 경우와 마찬가지로 `abstract` 속성과 연결 된 가상 디스패치 임을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-159">As with methods, `abstract` just means that there is a virtual dispatch associated with the property.</span></span> <span data-ttu-id="3566e-160">추상 속성은 동일한 클래스에 해당 정의 없이 즉, 실제로 추상 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-160">Abstract properties can be truly abstract, that is, without a definition in the same class.</span></span> <span data-ttu-id="3566e-161">따라서는 이러한 속성을 포함 하는 클래스는 추상 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-161">The class that contains such a property is therefore an abstract class.</span></span> <span data-ttu-id="3566e-162">또는 추상 속성은 가상, 및 경우에 정의에 있어야 동일한 클래스에만 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-162">Alternatively, abstract can just mean that a property is virtual, and in that case, a definition must be present in the same class.</span></span> <span data-ttu-id="3566e-163">추상 모니터링할 주의 추상 속성 private, 아니어야 하며 하나의 접근자 추상 이면 다른을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-163">Note that abstract properties must not be private, and if one accessor is abstract, the other must also be abstract.</span></span> <span data-ttu-id="3566e-164">추상 클래스에 대 한 자세한 내용은 참조 [추상 클래스](../abstract-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3566e-164">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a><span data-ttu-id="3566e-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3566e-165">See Also</span></span>
[<span data-ttu-id="3566e-166">멤버</span><span class="sxs-lookup"><span data-stu-id="3566e-166">Members</span></span>](index.md)

[<span data-ttu-id="3566e-167">메서드</span><span class="sxs-lookup"><span data-stu-id="3566e-167">Methods</span></span>](methods.md)
