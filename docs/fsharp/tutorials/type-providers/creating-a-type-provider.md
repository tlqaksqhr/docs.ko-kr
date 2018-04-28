---
title: '자습서: 형식 공급자 (F #) 만들기'
description: '기본 개념을 설명 하기 위해 몇 가지 간단한 형식 공급자를 검사 하 여 F # 3.0에 사용자 고유의 F # 형식 공급자를 만드는 방법을 설명 합니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: cea71a2b71f660971c1b2dde702c9b489be48cee
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="tutorial-create-a-type-provider"></a><span data-ttu-id="4e722-103">자습서: 형식 공급자 만들기</span><span class="sxs-lookup"><span data-stu-id="4e722-103">Tutorial: Create a Type Provider</span></span>

<span data-ttu-id="4e722-104">F # 형식 공급자 메커니즘에는 정보가 풍부한 프로그래밍에 대 한 지원의 중요 한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-104">The type provider mechanism in F# is a significant part of its support for information rich programming.</span></span> <span data-ttu-id="4e722-105">이 자습서에서는 개발의 기본 개념을 설명 하기 위해 몇 가지 단순 형식 공급자를 통해 사용자 고유의 형식 공급자를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-105">This tutorial explains how to create your own type providers by walking you through the development of several simple type providers to illustrate the basic concepts.</span></span> <span data-ttu-id="4e722-106">F # 형식 공급자 메커니즘에 대 한 자세한 내용은 참조 [형식 공급자](index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-106">For more information about the type provider mechanism in F#, see [Type Providers](index.md).</span></span>

<span data-ttu-id="4e722-107">F # 생태계는 자주 사용 되는 인터넷 및 엔터프라이즈 데이터 서비스에 대 한 형식 공급자의 범위를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-107">The F# ecosystem contains a range of type providers for commonly used Internet and enterprise data services.</span></span> <span data-ttu-id="4e722-108">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="4e722-108">For example:</span></span>

- <span data-ttu-id="4e722-109">[FSharp.Data](https://fsharp.github.io/FSharp.Data/) 문서 형식을 JSON, XML, CSV 및 HTML에 대 한 형식 공급자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-109">[FSharp.Data](https://fsharp.github.io/FSharp.Data/) includes type providers for JSON, XML, CSV and HTML document formats.</span></span>

- <span data-ttu-id="4e722-110">[SQLProvider](https://fsprojects.github.io/SQLProvider/) 이러한 데이터 원본에 대 한 쿼리 개체의 매핑 및 F # LINQ를 통해 SQL 데이터베이스에 대 한 강력한 형식의 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-110">[SQLProvider](https://fsprojects.github.io/SQLProvider/) provides strongly-typed access to SQL databases through a object mapping and F# LINQ queries against these data sources.</span></span>

- <span data-ttu-id="4e722-111">[FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) 컴파일 시간에 대 한 형식 공급자 집합을 체크 F #에서 T-SQL의 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-111">[FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) has a set of type providers for compile-time checked embedding of T-SQL in F#.</span></span>

- <span data-ttu-id="4e722-112">[FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) SQL, Entity Framework, OData와 WSDL 데이터 서비스에 액세스 하기 위한.NET Framework 프로그래밍에만 사용 하기 위해 형식 공급자의 이전 버전 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-112">[FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) is an older set of type providers for use only with .NET Framework programming for accessing SQL, Entity Framework, OData and WSDL data services.</span></span>

<span data-ttu-id="4e722-113">필요한 경우 사용자 지정 형식 공급자를 만들거나 다른 사람이 만든 형식 공급자를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-113">Where necessary, you can create custom type providers, or you can reference type providers that others have created.</span></span> <span data-ttu-id="4e722-114">예를 들어 조직에는 자체 안정적인 데이터 스키마와 함께 각 명명 된 데이터 집합의 크기가 크고 점점 여러 제공 하는 데이터 서비스가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-114">For example, your organization could have a data service that provides a large and growing number of named data sets, each with its own stable data schema.</span></span> <span data-ttu-id="4e722-115">스키마를 읽고 프로그래머에 게 강력한 형식의 방식으로 현재 데이터 집합을 제공 하는 형식 공급자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-115">You can create a type provider that reads the schemas and presents the current data sets to the programmer in a strongly typed way.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="4e722-116">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="4e722-116">Before You Start</span></span>

<span data-ttu-id="4e722-117">F # 프로그래밍 경험에 안정적인 데이터 및 서비스 정보 공간 삽입에 대 한 형식 공급자 메커니즘은 주로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-117">The type provider mechanism is primarily designed for injecting stable data and service information spaces into the F# programming experience.</span></span>

<span data-ttu-id="4e722-118">이 메커니즘 프로그램 논리에 관련 된 방법으로 프로그램 실행 중에 있는 스키마의 변경 내용은 공백 삽입 위해 설계 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-118">This mechanism isn’t designed for injecting information spaces whose schema changes during program execution in ways that are relevant to program logic.</span></span> <span data-ttu-id="4e722-119">또한 메커니즘은 해당 도메인 몇 가지 올바른 사용을 포함 하는 경우에 메타 프로그래밍 내 언어에 대 한 설계 되지 않은 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-119">Also, the mechanism isn't designed for intra-language meta-programming, even though that domain contains some valid uses.</span></span> <span data-ttu-id="4e722-120">필요한 경우에이 메커니즘을 사용 해야 하 고 형식 공급자를 개발 매우 높은 값을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-120">You should use this mechanism only where necessary and where the development of a type provider yields very high value.</span></span>

<span data-ttu-id="4e722-121">스키마를 사용할 수 없는 형식 공급자를 작성 하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-121">You should avoid writing a type provider where a schema isn't available.</span></span> <span data-ttu-id="4e722-122">일반 (또는 기존의)를 한 형식 공급자를 작성 하지 말아야 마찬가지로,.NET 라이브러리를 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-122">Likewise, you should avoid writing a type provider where an ordinary (or even an existing) .NET library would suffice.</span></span>

<span data-ttu-id="4e722-123">시작 하기 전에 다음 질문 수 있습니다.:</span><span class="sxs-lookup"><span data-stu-id="4e722-123">Before you start, you might ask the following questions:</span></span>

- <span data-ttu-id="4e722-124">정보 원본에 대 한 스키마 있습니까?</span><span class="sxs-lookup"><span data-stu-id="4e722-124">Do you have a schema for your information source?</span></span> <span data-ttu-id="4e722-125">이 경우에 F # 및.NET 형식 시스템 매핑 이란?</span><span class="sxs-lookup"><span data-stu-id="4e722-125">If so, what’s the mapping into the F# and .NET type system?</span></span>

- <span data-ttu-id="4e722-126">사용할 수 있는 기존 (동적으로 형식화 된) API 시작 지점으로 구현에 대 한?</span><span class="sxs-lookup"><span data-stu-id="4e722-126">Can you use an existing (dynamically typed) API as a starting point for your implementation?</span></span>

- <span data-ttu-id="4e722-127">사용자와 사용자 조직이 쉽게 작성 하 고 좋은지를 형식 공급자의 충분 한 용도 미치나요?</span><span class="sxs-lookup"><span data-stu-id="4e722-127">Will you and your organization have enough uses of the type provider to make writing it worthwhile?</span></span> <span data-ttu-id="4e722-128">일반.NET 라이브러리 요구 사항 충족?</span><span class="sxs-lookup"><span data-stu-id="4e722-128">Would a normal .NET library meet your needs?</span></span>

- <span data-ttu-id="4e722-129">스키마 변경 얼마나 되나요?</span><span class="sxs-lookup"><span data-stu-id="4e722-129">How much will your schema change?</span></span>

- <span data-ttu-id="4e722-130">코딩 하는 동안 변경 되나요?</span><span class="sxs-lookup"><span data-stu-id="4e722-130">Will it change during coding?</span></span>

- <span data-ttu-id="4e722-131">코딩 세션 간에 변경 되나요?</span><span class="sxs-lookup"><span data-stu-id="4e722-131">Will it change between coding sessions?</span></span>

- <span data-ttu-id="4e722-132">프로그램 실행 중 변경 되나요?</span><span class="sxs-lookup"><span data-stu-id="4e722-132">Will it change during program execution?</span></span>

<span data-ttu-id="4e722-133">형식 공급자는 스키마는 런타임 시 및 컴파일된 코드의 수명 동안 안정적인 상황에 가장 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-133">Type providers are best suited to situations where the schema is stable at runtime and during the lifetime of compiled code.</span></span>


## <a name="a-simple-type-provider"></a><span data-ttu-id="4e722-134">단순 형식 공급자</span><span class="sxs-lookup"><span data-stu-id="4e722-134">A Simple Type Provider</span></span>

<span data-ttu-id="4e722-135">이 샘플은 샘플에서는 비슷한 Samples.HelloWorldTypeProvider는 `examples` 의 디렉터리는 [F # 형식 공급자 SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/)합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-135">This sample is Samples.HelloWorldTypeProvider, similar to the samples in the `examples` directory of the [F# Type Provider SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/).</span></span> <span data-ttu-id="4e722-136">공급자 있게 사용할 수 있는 F # 시그니처 구문을 사용 하 고을 제외한 모든 페이지에 대 한 세부 정보를 생략 하 여 다음 코드 에서처럼 100 지워진된 형식을 포함 하는 "유형 공간" `Type1`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-136">The provider makes available a "type space" that contains 100 erased types, as the following code shows by using F# signature syntax and omitting the details for all except `Type1`.</span></span> <span data-ttu-id="4e722-137">지워진된 형식에 대 한 자세한 내용은 참조 [세부 정보에 대 한 지워진 제공 된 형식](#details-about-erased-provided-types) 이 항목의 뒷부분에 나오는 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-137">For more information about erased types, see [Details About Erased Provided Types](#details-about-erased-provided-types) later in this topic.</span></span>

```fsharp
namespace Samples.HelloWorldTypeProvider

type Type1 =
    /// This is a static property.
    static member StaticProperty : string

    /// This constructor takes no arguments.
    new : unit -> Type1

    /// This constructor takes one argument.
    new : data:string -> Type1

    /// This is an instance property.
    member InstanceProperty : int

    /// This is an instance method.
    member InstanceMethod : x:int -> char

    /// This is an instance property.
    nested type NestedType = 
        /// This is StaticProperty1 on NestedType.
        static member StaticProperty1 : string
        …
        /// This is StaticProperty100 on NestedType.
        static member StaticProperty100 : string

type Type2 =
…
…

type Type100 =
…
```

<span data-ttu-id="4e722-138">형식 및 제공 하는 멤버 집합을 정적으로 알려져 있는지 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-138">Note that the set of types and members provided is statically known.</span></span> <span data-ttu-id="4e722-139">이 예제에서는 공급자의 스키마에 의존 하는 형식을 제공 하도록 기능 활용</span><span class="sxs-lookup"><span data-stu-id="4e722-139">This example doesn't leverage the ability of providers to provide types that depend on a schema.</span></span> <span data-ttu-id="4e722-140">다음 코드에서 형식 공급자의 구현 방법이 나와 있는 및 세부 정보는이 항목의 뒷부분에 나오는 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-140">The implementation of the type provider is outlined in the following code, and the details are covered in later sections of this topic.</span></span>


>[!WARNING] 
<span data-ttu-id="4e722-141">이 코드와 온라인 샘플 간의 차이가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-141">There may be differences between this code and the online samples.</span></span>

```fsharp
namespace Samples.FSharp.HelloWorldTypeProvider

open System
open System.Reflection
open ProviderImplementation.ProvidedTypes
open FSharp.Core.CompilerServices
open FSharp.Quotations

// This type defines the type provider. When compiled to a DLL, it can be added
// as a reference to an F# command-line compilation, script, or project.
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this = 

  // Inheriting from this type provides implementations of ITypeProvider 
  // in terms of the provided types below.
  inherit TypeProviderForNamespaces(config)

  let namespaceName = "Samples.HelloWorldTypeProvider"
  let thisAssembly = Assembly.GetExecutingAssembly()

  // Make one provided type, called TypeN.
  let makeOneProvidedType (n:int) = 
  …
  // Now generate 100 types
  let types = [ for i in 1 .. 100 -> makeOneProvidedType i ] 

  // And add them to the namespace
  do this.AddNamespace(namespaceName, types)

[<assembly:TypeProviderAssembly>] 
do()
```

<span data-ttu-id="4e722-142">이 공급자를 사용 하려면 Visual Studio의 개별 인스턴스를 열고 F # 스크립트를 만들 후 다음 코드 에서처럼 #r을 사용 하 여 스크립트에서 공급자에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-142">To use this provider, open a separate instance of Visual Studio, create an F# script, and then add a reference to the provider from your script by using #r as the following code shows:</span></span>

```fsharp
#r @".\bin\Debug\Samples.HelloWorldTypeProvider.dll"

let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")

let obj2 = Samples.HelloWorldTypeProvider.Type1("some other data")

obj1.InstanceProperty
obj2.InstanceProperty

[ for index in 0 .. obj1.InstanceProperty-1 -> obj1.InstanceMethod(index) ]
[ for index in 0 .. obj2.InstanceProperty-1 -> obj2.InstanceMethod(index) ]

let data1 = Samples.HelloWorldTypeProvider.Type1.NestedType.StaticProperty35
```

<span data-ttu-id="4e722-143">그런 다음 아래 형식을 찾습니다는 `Samples.HelloWorldTypeProvider` 형식 공급자가 생성 되는 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-143">Then look for the types under the `Samples.HelloWorldTypeProvider` namespace that the type provider generated.</span></span>

<span data-ttu-id="4e722-144">공급자를 다시 컴파일하기 전에 공급자 DLL을 사용 하는 Visual Studio 및 F # Interactive의 모든 인스턴스를 닫았는지 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-144">Before you recompile the provider, make sure that you have closed all instances of Visual Studio and F# Interactive that are using the provider DLL.</span></span> <span data-ttu-id="4e722-145">그렇지 않으면 DLL 출력에 잠깁니다 때문에 빌드 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-145">Otherwise, a build error will occur because the output DLL will be locked.</span></span>

<span data-ttu-id="4e722-146">인쇄 문을 사용 하 여이 공급자를 디버깅 하려면 공급자를 문제가 노출 하는 스크립트를 만들고 다음 코드를 사용 하 여:</span><span class="sxs-lookup"><span data-stu-id="4e722-146">To debug this provider by using print statements, make a script that exposes a problem with the provider, and then use the following code:</span></span>

```fsharp
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="4e722-147">Visual Studio를 사용 하 여이 공급자를 디버깅 하려면 관리자 자격 증명으로 Visual Studio 명령 프롬프트를 열고 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-147">To debug this provider by using Visual Studio, open the Visual Studio command prompt with administrative credentials, and run the following command:</span></span>

```fsharp
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="4e722-148">대신, Visual Studio를 열고, 디버그 메뉴를 열고, 선택 `Debug/Attach to process…`, 및 다른 연결 `devenv` 스크립트를 편집 하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-148">As an alternative, open Visual Studio, open the Debug menu, choose `Debug/Attach to process…`, and attach to another `devenv` process where you’re editing your script.</span></span> <span data-ttu-id="4e722-149">이 메서드를 사용 하 여 대화형으로 식을 전체 IntelliSense 및 기타 기능) (사용 하 여 두 번째 인스턴스를 입력 하 여 형식 공급자에서 특정 논리를 보다 쉽게 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-149">By using this method, you can more easily target particular logic in the type provider by interactively typing expressions into the second instance (with full IntelliSense and other features).</span></span>

<span data-ttu-id="4e722-150">생성 된 코드의에서 오류를 확인 하는 데를 디버깅 하는 내 코드만 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-150">You can disable Just My Code debugging to better identify errors in generated code.</span></span> <span data-ttu-id="4e722-151">사용 하도록 설정 하거나이 기능을 사용 하지 않도록 설정 하는 방법에 대 한 정보를 참조 하십시오. [디버거로 코드 탐색](/visualstudio/debugger/navigating-through-code-with-the-debugger)합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-151">For information about how to enable or disable this feature, see [Navigating through Code with the Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span></span> <span data-ttu-id="4e722-152">첫째 예외를 열어 알림도 설정할 수는 또한는 `Debug` 메뉴를 선택한 다음 `Exceptions` 또는를 열려면 Ctrl + Alt + E 키를 선택 하 여는 `Exceptions` 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="4e722-152">Also, you can also set first-chance exception catching by opening the `Debug` menu and then choosing `Exceptions` or by choosing the Ctrl+Alt+E keys to open the `Exceptions` dialog box.</span></span> <span data-ttu-id="4e722-153">해당 대화 상자에서 아래 `Common Language Runtime Exceptions`, 선택는 `Thrown` 확인란 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-153">In that dialog box, under `Common Language Runtime Exceptions`, select the `Thrown` check box.</span></span>


### <a name="implementation-of-the-type-provider"></a><span data-ttu-id="4e722-154">형식 공급자의 구현</span><span class="sxs-lookup"><span data-stu-id="4e722-154">Implementation of the Type Provider</span></span>

<span data-ttu-id="4e722-155">이 섹션에서는 구현 된 형식 공급자의 주 섹션을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-155">This section walks you through the principal sections of the type provider implementation.</span></span> <span data-ttu-id="4e722-156">첫째, 자체 사용자 지정 형식 공급자에 대 한 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-156">First, you define the type for the custom type provider itself:</span></span>

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

<span data-ttu-id="4e722-157">이 형식은 public 이어야 하 고으로 표시 해야는 [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) 특성 유형을 포함 하는 어셈블리를 참조 하는 별도 F # 프로젝트 컴파일러에서 형식 공급자를 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-157">This type must be public, and you must mark it with the [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) attribute so that the compiler will recognize the type provider when a separate F# project references the assembly that contains the type.</span></span> <span data-ttu-id="4e722-158">*config* 매개 변수는 선택 사항이 고, 있는 경우 F # 컴파일러에서 만들어지는 형식 공급자 인스턴스에 대 한 상황에 맞는 구성 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-158">The *config* parameter is optional, and, if present, contains contextual configuration information for the type provider instance that the F# compiler creates.</span></span>

<span data-ttu-id="4e722-159">구현 하는 다음으로 [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-159">Next, you implement the [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) interface.</span></span> <span data-ttu-id="4e722-160">사용 하는 경우에 `TypeProviderForNamespaces` 에서 유형을 `ProvidedTypes` 기본 형식으로는 API입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-160">In this case, you use the `TypeProviderForNamespaces` type from the `ProvidedTypes` API as a base type.</span></span> <span data-ttu-id="4e722-161">이 도우미 형식은 네임 스페이스를 각각 포함 하는 직접 한정 된 수의 고정을 적극적으로 제공 된 형식 제공 적극적으로 한정 된 컬렉션을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-161">This helper type can provide a finite collection of eagerly provided namespaces, each of which directly contains a finite number of fixed, eagerly provided types.</span></span> <span data-ttu-id="4e722-162">이 컨텍스트에서 공급자 *적극적으로* 필요 없습니다. 하거나 사용 하는 경우에 형식을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-162">In this context, the provider *eagerly* generates types even if they aren't needed or used.</span></span>

```fsharp
inherit TypeProviderForNamespaces(config)
```

<span data-ttu-id="4e722-163">다음으로 제공 된 형식에 대 한 네임 스페이스를 지정 하는 로컬 개인 값을 정의 하 고 자체 형식 공급자 어셈블리를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-163">Next, define local private values that specify the namespace for the provided types, and find the type provider assembly itself.</span></span> <span data-ttu-id="4e722-164">이 어셈블리는 제공 되는 지워진된 형식의 논리적 부모 멤버가 형식으로 나중에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-164">This assembly is used later as the logical parent type of the erased types that are provided.</span></span>

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

<span data-ttu-id="4e722-165">다음으로 각 Type1 유형을 제공 하는 함수를 만들기... Type100 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-165">Next, create a function to provide each of the types Type1…Type100.</span></span> <span data-ttu-id="4e722-166">이 함수는이 항목의 뒷부분에서 자세히 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-166">This function is explained in more detail later in this topic.</span></span>

```fsharp
let makeOneProvidedType (n:int) = …
```

<span data-ttu-id="4e722-167">다음으로 100 제공 된 형식을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-167">Next, generate the 100 provided types:</span></span>

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

<span data-ttu-id="4e722-168">다음에 제공 된 네임 스페이스도 형식을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-168">Next, add the types as a provided namespace:</span></span>

```fsharp
do this.AddNamespace(namespaceName, types)
```

<span data-ttu-id="4e722-169">마지막으로, 형식 공급자 DLL을 만드는 것을 나타내는 어셈블리 특성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-169">Finally, add an assembly attribute that indicates that you are creating a type provider DLL:</span></span>

```fsharp
[<assembly:TypeProviderAssembly>] 
do()
```

### <a name="providing-one-type-and-its-members"></a><span data-ttu-id="4e722-170">한 형식 및 해당 멤버를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-170">Providing One Type And Its Members</span></span>

<span data-ttu-id="4e722-171">`makeOneProvidedType` 함수 유형 중 하나를 제공 하는 중 실제 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-171">The `makeOneProvidedType` function does the real work of providing one of the types.</span></span>

```fsharp
let makeOneProvidedType (n:int) = 
…
```

<span data-ttu-id="4e722-172">이 단계에서는이 함수를 구현에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-172">This step explains the implementation of this function.</span></span> <span data-ttu-id="4e722-173">먼저 제공 된 형식 만듭니다 (예: Type1, n = 1 또는 Type57, n = 57).</span><span class="sxs-lookup"><span data-stu-id="4e722-173">First, create the provided type (for example, Type1, when n = 1, or Type57, when n = 57).</span></span>

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code, 
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

<span data-ttu-id="4e722-174">다음 사항을 유념 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4e722-174">You should note the following points:</span></span>

- <span data-ttu-id="4e722-175">이 제공 유형 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-175">This provided type is erased.</span></span>  <span data-ttu-id="4e722-176">기본 형식이 나타내기 때문에 `obj`, 인스턴스 형식의 값으로 표시 됩니다 [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) 컴파일된 코드에서.</span><span class="sxs-lookup"><span data-stu-id="4e722-176">Because you indicate that the base type is `obj`, instances will appear as values of type [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) in compiled code.</span></span>

- <span data-ttu-id="4e722-177">중첩 되지 않은 형식을 지정 하면, 어셈블리 및 네임 스페이스를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-177">When you specify a non-nested type, you must specify the assembly and namespace.</span></span> <span data-ttu-id="4e722-178">지워진된 형식에 대 한 어셈블리 유형 공급자 어셈블리 자체 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-178">For erased types, the assembly should be the type provider assembly itself.</span></span>

<span data-ttu-id="4e722-179">다음으로 XML 문서 형식에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-179">Next, add XML documentation to the type.</span></span> <span data-ttu-id="4e722-180">이 설명서 즉 지연 되 고, 호스트 컴파일러에서 필요한 경우 주문형을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-180">This documentation is delayed, that is, computed on-demand if the host compiler needs it.</span></span>

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

<span data-ttu-id="4e722-181">다음 형식으로 제공 된 정적 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-181">Next you add a provided static property to the type:</span></span>

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty", 
                                  propertyType = typeof<string>, 
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

<span data-ttu-id="4e722-182">이 속성은 항상 "Hello!" 문자열을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-182">Getting this property will always evaluate to the string "Hello!".</span></span> <span data-ttu-id="4e722-183">`GetterCode` 는 F # 인용을 나타내는 속성을 가져오기 위한 호스트 컴파일러에서 생성 하는 코드를 사용 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-183">The `GetterCode` for the property uses an F# quotation, which represents the code that the host compiler generates for getting the property.</span></span> <span data-ttu-id="4e722-184">인용구에 대 한 자세한 내용은 참조 [코드 인용 (F #)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155)합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-184">For more information about quotations, see [Code Quotations (F#)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).</span></span>

<span data-ttu-id="4e722-185">속성에 XML 문서를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-185">Add XML documentation to the property.</span></span>

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

<span data-ttu-id="4e722-186">이제 제공 된 형식으로 제공된 된 속성을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-186">Now attach the provided property to the provided type.</span></span> <span data-ttu-id="4e722-187">하나의 형식으로 제공 된 멤버를 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-187">You must attach a provided member to one and only one type.</span></span> <span data-ttu-id="4e722-188">그렇지 않으면 멤버가 액세스할 수 있는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-188">Otherwise, the member will never be accessible.</span></span>

```fsharp
t.AddMember staticProp
```

<span data-ttu-id="4e722-189">이제 매개 변수를 사용 하는 제공 된 생성자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-189">Now create a provided constructor that takes no parameters.</span></span>

```fsharp
let ctor = ProvidedConstructor(parameters = [ ], 
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

<span data-ttu-id="4e722-190">`InvokeCode` 는 F # 인용에 생성자를 호출 하는 경우 호스트 컴파일러에서 생성 하는 코드를 나타내는 반환 하는 생성자에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-190">The `InvokeCode` for the constructor returns an F# quotation, which represents the code that the host compiler generates when the constructor is called.</span></span> <span data-ttu-id="4e722-191">예를 들어 다음 생성자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-191">For example, you can use the following constructor:</span></span>

```fsharp
new Type10()
```

<span data-ttu-id="4e722-192">제공 된 형식의 인스턴스를 기본 데이터와 "개체 데이터" 만들 수 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-192">An instance of the provided type will be created with underlying data "The object data".</span></span> <span data-ttu-id="4e722-193">따옴표 붙은 코드에 대 한 변환에 [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) 해당 형식으로 지울 이므로이 제공 된 형식 (지정한 것과 제공 된 형식 선언 때).</span><span class="sxs-lookup"><span data-stu-id="4e722-193">The quoted code includes a conversion to [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) because that type is the erasure of this provided type (as you specified when you declared the provided type).</span></span>

<span data-ttu-id="4e722-194">생성자에 XML 문서를 추가 하 고 제공 된 형식으로 제공 된 생성자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-194">Add XML documentation to the constructor, and add the provided constructor to the provided type:</span></span>

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

<span data-ttu-id="4e722-195">매개 변수를 사용 하는 두 번째 제공 된 생성자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-195">Create a second provided constructor that takes one parameter:</span></span>

```fsharp
let ctor2 = 
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ], 
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

<span data-ttu-id="4e722-196">`InvokeCode` 는 F # 인용을 나타내는 메서드에 대 한 호출에 대 한 호스트 컴파일러에서 생성 하는 코드를 다시 반환 하는 생성자에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-196">The `InvokeCode` for the constructor again returns an F# quotation, which represents the code that the host compiler generated for a call to the method.</span></span> <span data-ttu-id="4e722-197">예를 들어 다음 생성자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-197">For example, you can use the following constructor:</span></span>

```fsharp
new Type10("ten")
```

<span data-ttu-id="4e722-198">제공 된 형식의 인스턴스는 기본 데이터 "10"으로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-198">An instance of the provided type is created with underlying data "ten".</span></span> <span data-ttu-id="4e722-199">하면 이미 로드 된는 `InvokeCode` 함수 인용을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-199">You may have already noticed that the `InvokeCode` function returns a quotation.</span></span> <span data-ttu-id="4e722-200">이 함수에 대 한 입력은 하나씩 생성자 매개 변수 식의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-200">The input to this function is a list of expressions, one per constructor parameter.</span></span> <span data-ttu-id="4e722-201">이 경우 단일 매개 변수 값을 나타내는 식에서 사용할 수는 `args.[0]`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-201">In this case, an expression that represents the single parameter value is available in `args.[0]`.</span></span> <span data-ttu-id="4e722-202">생성자에 대 한 호출에 대 한 코드에 반환 값을 지우고 형식 강제 변환 `obj`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-202">The code for a call to the constructor coerces the return value to the erased type `obj`.</span></span> <span data-ttu-id="4e722-203">제공 된 두 번째 생성자는 형식에 추가한 후 제공 된 인스턴스 속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-203">After you add the second provided constructor to the type, you create a provided instance property:</span></span>

```fsharp
let instanceProp = 
    ProvidedProperty(propertyName = "InstanceProperty", 
                     propertyType = typeof<int>, 
                     getterCode= (fun args -> 
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

<span data-ttu-id="4e722-204">이 속성을 가져오는 위에 있는 개체가 표시 되는 문자열의 길이 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-204">Getting this property will return the length of the string, which is the representation object.</span></span> <span data-ttu-id="4e722-205">`GetterCode` 속성 속성을 가져오는 호스트 컴파일러에서 생성 하는 코드를 지정 하는 F # 인용을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-205">The `GetterCode` property returns an F# quotation that specifies the code that the host compiler generates to get the property.</span></span> <span data-ttu-id="4e722-206">마찬가지로 `InvokeCode`, `GetterCode` 함수 인용을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-206">Like `InvokeCode`, the `GetterCode` function returns a quotation.</span></span> <span data-ttu-id="4e722-207">호스트 컴파일러는 인수 목록으로이 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-207">The host compiler calls this function with a list of arguments.</span></span> <span data-ttu-id="4e722-208">인수는 getter가 호출 되 고, 사용 하 여 액세스할 수 있는 인스턴스를 나타내는 단일 식만 포함 하는 경우에 `args.[0]`합니다. 구현 `GetterCode` 지워진 형식을 결과 인용에 분할 한 다음 `obj`, 캐스트는 문자열은 형식 검사에 대 한 컴파일러의 메커니즘을 충족 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-208">In this case, the arguments include just the single expression that represents the instance upon which the getter is being called, which you can access by using `args.[0]`.The implementation of `GetterCode` then splices into the result quotation at the erased type `obj`, and a cast is used to satisfy the compiler's mechanism for checking types that the object is a string.</span></span> <span data-ttu-id="4e722-209">다음 부분이 `makeOneProvidedType` 매개 변수를 사용 하 여 인스턴스 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-209">The next part of `makeOneProvidedType` provides an instance method with one parameter.</span></span>

```fsharp
let instanceMeth = 
    ProvidedMethod(methodName = "InstanceMethod", 
                   parameters = [ProvidedParameter("x",typeof<int>)], 
                   returnType = typeof<char>, 
                   invokeCode = (fun args -> 
                       <@@ ((%%(args.[0]) : obj) :?> string).Chars(%%(args.[1]) : int) @@>))

instanceMeth.AddXmlDocDelayed(fun () -> "This is an instance method")
// Add the instance method to the type.
t.AddMember instanceMeth
```

<span data-ttu-id="4e722-210">마지막으로 100 중첩 된 속성을 포함 하는 중첩된 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-210">Finally, create a nested type that contains 100 nested properties.</span></span> <span data-ttu-id="4e722-211">이 만들지 중첩 유형 및 속성 즉 지연 되 고, 주문형으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-211">The creation of this nested type and its properties is delayed, that is, computed on-demand.</span></span>

```fsharp
t.AddMembersDelayed(fun () -> 
  let nestedType = ProvidedTypeDefinition("NestedType", Some typeof<obj>)

  nestedType.AddMembersDelayed (fun () -> 
    let staticPropsInNestedType = 
      [ for i in 1 .. 100 do
          let valueOfTheProperty = "I am string "  + string i

          let p = 
            ProvidedProperty(propertyName = "StaticProperty" + string i, 
              propertyType = typeof<string>, 
              isStatic = true,
              getterCode= (fun args -> <@@ valueOfTheProperty @@>))

          p.AddXmlDocDelayed(fun () -> 
              sprintf "This is StaticProperty%d on NestedType" i)

          yield p ]

    staticPropsInNestedType)

  [nestedType])
```

### <a name="details-about-erased-provided-types"></a><span data-ttu-id="4e722-212">지워진된 제공 된 형식에 대 한 세부 정보</span><span class="sxs-lookup"><span data-stu-id="4e722-212">Details about Erased Provided Types</span></span>

<span data-ttu-id="4e722-213">이 섹션의 예제만 제공 *제공 된 형식을 지울*, 하는 다음과 같은 경우에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-213">The example in this section provides only *erased provided types*, which are particularly useful in the following situations:</span></span>

- <span data-ttu-id="4e722-214">데이터와 메서드를 포함 하는 정보 공간에 대 한 공급자 작성할 때는.</span><span class="sxs-lookup"><span data-stu-id="4e722-214">When you are writing a provider for an information space that contains only data and methods.</span></span>

- <span data-ttu-id="4e722-215">정확한 런타임 형식 의미 체계 정보 공간의 실용적인 사용에 대 한 중요 하지 않은 공급자 작성할 때는.</span><span class="sxs-lookup"><span data-stu-id="4e722-215">When you are writing a provider where accurate runtime-type semantics aren't critical for practical use of the information space.</span></span>

- <span data-ttu-id="4e722-216">매우 큰 하 고 상호 연결 된 정보 공간에 대 한 실제.NET 형식을 생성 하는 기술적으로 가능 하지 않은 정보 공간에 대 한 공급자 작성할 때는.</span><span class="sxs-lookup"><span data-stu-id="4e722-216">When you are writing a provider for an information space that is so large and interconnected that it isn’t technically feasible to generate real .NET types for the information space.</span></span>

<span data-ttu-id="4e722-217">이 예제에서는 제공 된 각 형식으로 형식 지워집니다 `obj`, 유형에 사용 되는 모든 형식으로 표시 됩니다 `obj` 컴파일된 코드에서.</span><span class="sxs-lookup"><span data-stu-id="4e722-217">In this example, each provided type is erased to type `obj`, and all uses of the type will appear as type `obj` in compiled code.</span></span> <span data-ttu-id="4e722-218">실제로 이러한 예제에서 원본 개체는 문자열 이지만 형식으로 나타납니다. `System.Object` .net에서 컴파일된 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-218">In fact, the underlying objects in these examples are strings, but the type will appear as `System.Object` in .NET compiled code.</span></span> <span data-ttu-id="4e722-219">형식 삭제에 대 한 모든 사용 명시적 boxing을 사용할 수 있는, unboxing 하 고 캐스팅 방해할를 지울 형식.</span><span class="sxs-lookup"><span data-stu-id="4e722-219">As with all uses of type erasure, you can use explicit boxing, unboxing, and casting to subvert erased types.</span></span> <span data-ttu-id="4e722-220">이 경우에 개체가 사용 된 경우 유효 하지 않은 캐스팅 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-220">In this case, a cast exception that isn’t valid may result when the object is used.</span></span> <span data-ttu-id="4e722-221">공급자 런타임 false 표현 으로부터 보호 하려면 고유한 개인 표현 종류를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-221">A provider runtime can define its own private representation type to help protect against false representations.</span></span> <span data-ttu-id="4e722-222">F # 자체에서 지워진된 종류를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-222">You can’t define erased types in F# itself.</span></span> <span data-ttu-id="4e722-223">제공 된 형식은 삭제 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-223">Only provided types may be erased.</span></span> <span data-ttu-id="4e722-224">모두 유용한 결과 이해 해야 하 고 지워진된 형식 형식 공급자 또는 제공 하는 공급자에 대 한 삭제 형식 중 하나를 사용 하 여 의미 체계입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-224">You must understand the ramifications, both practical and semantic, of using either erased types for your type provider or a provider that provides erased types.</span></span> <span data-ttu-id="4e722-225">지워진된 형식을 실제.NET 형식이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-225">An erased type has no real .NET type.</span></span> <span data-ttu-id="4e722-226">따라서는 형식에 대해 정확 하 게 반영을 할 수 없습니다 및 런타임 캐스팅이 및 정확한 런타임 형식 의미 체계를 사용 하는 기타 기술을 사용 하는 경우에 지워진된 종류를 방해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-226">Therefore, you cannot do accurate reflection over the type, and you might subvert erased types if you use runtime casts and other techniques that rely on exact runtime type semantics.</span></span> <span data-ttu-id="4e722-227">지워진 형식의 subversion 런타임에 형식 캐스팅 예외가 자주 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-227">Subversion of erased types frequently results in type cast exceptions at runtime.</span></span>


### <a name="choosing-representations-for-erased-provided-types"></a><span data-ttu-id="4e722-228">제공 된 형식 삭제에 대 한 표현을 선택</span><span class="sxs-lookup"><span data-stu-id="4e722-228">Choosing Representations for Erased Provided Types</span></span>

<span data-ttu-id="4e722-229">지워진 제공 된 형식의 몇 가지 용도로 나타나지가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-229">For some uses of erased provided types, no representation is required.</span></span> <span data-ttu-id="4e722-230">예를 들어는 지워진 제공 정적 속성 및 멤버 및 생성자 없음 형식이 포함 될 수 있으며 메서드나 속성이 없는 형식의 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-230">For example, the erased provided type might contain only static properties and members and no constructors, and no methods or properties would return an instance of the type.</span></span> <span data-ttu-id="4e722-231">수에 도달 하면 인스턴스는 지워진된 제공 된 형식에는 다음 질문을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-231">If you can reach instances of an erased provided type, you must consider the following questions:</span></span>

<span data-ttu-id="4e722-232">**제공된 된 형식으로 지울 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="4e722-232">**What is the erasure of a provided type?**</span></span>

- <span data-ttu-id="4e722-233">제공된 된 형식으로 지울 유형이 컴파일된.NET 코드에 표시 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-233">The erasure of a provided type is how the type appears in compiled .NET code.</span></span>

- <span data-ttu-id="4e722-234">지워진된 제공 된 클래스 형식의 삭제는 항상 첫 번째 비 지울 기본 형식 상속 체인에 형식의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-234">The erasure of a provided erased class type is always the first non-erased base type in the inheritance chain of the type.</span></span>

- <span data-ttu-id="4e722-235">지워진된 제공 된 인터페이스 형식의 삭제는 항상 `System.Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-235">The erasure of a provided erased interface type is always `System.Object`.</span></span>

<span data-ttu-id="4e722-236">**제공된 된 형식 표현을 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="4e722-236">**What are the representations of a provided type?**</span></span>

- <span data-ttu-id="4e722-237">지워진 제공 된 형식에 대 한 가능한 개체 집합이 표현 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-237">The set of possible objects for an erased provided type are called its representations.</span></span> <span data-ttu-id="4e722-238">이 문서의 예제에서는 표현을 지워진 제공 된 모든 형식을 `Type1..Type100` 는 항상 string 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-238">In the example in this document, the representations of all the erased provided types `Type1..Type100` are always string objects.</span></span>

<span data-ttu-id="4e722-239">제공 된 형식의 모든 표현으로 제공된 된 형식 지울 호환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-239">All representations of a provided type must be compatible with the erasure of the provided type.</span></span> <span data-ttu-id="4e722-240">(그렇지 않으면 F # 컴파일러에서 형식 공급자의 사용에 대 한 오류를 제공 합니다 또는 유효 하지 않은 비안정형.NET 코드가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-240">(Otherwise, either the F# compiler will give an error for a use of the type provider, or unverifiable .NET code that isn't valid will be generated.</span></span> <span data-ttu-id="4e722-241">형식 공급자는 유효하지 않은 표현을 제공하는 코드를 반환하는 경우 사용할 수 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="4e722-241">A type provider isn’t valid if it returns code that gives a  representation that isn't valid.)</span></span>

<span data-ttu-id="4e722-242">제공 된 개체에 대 한 표현 되는 매우 일반적인 다음 방법 중 하나를 사용 하 여 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-242">You can choose a representation for provided objects by using either of the following approaches, both of which are very common:</span></span>

- <span data-ttu-id="4e722-243">강력한 형식의 래퍼를 제공 하는 기존.NET 형식에 대해 단순히 하는 경우 경향이 있으므로 지울 해당 형식으로, 해당 형식의 인스턴스를 사용 하 여 표현 또는 둘 다로 사용자 형식에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-243">If you're simply providing a strongly typed wrapper over an existing .NET type, it often makes sense for your type to erase to that type, use instances of that type as representations, or both.</span></span> <span data-ttu-id="4e722-244">이 접근 방식은 대부분의 해당 형식에 기존 메서드는 여전히 하는 경우에 강력한 형식의 버전을 사용 하는 경우에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-244">This approach is appropriate when most of the existing methods on that type still make sense when using the strongly typed version.</span></span>

- <span data-ttu-id="4e722-245">기존.NET API에서 다른 API를 크게 만들기 하려는 경우는 유형 삭제 하 고 제공 된 형식에 대 한 표현이 될 런타임 형식을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-245">If you want to create an API that differs significantly from any existing .NET API, it makes sense to create runtime types that will be the type erasure and representations for the provided types.</span></span>

<span data-ttu-id="4e722-246">이 문서의 예제에서는 제공 된 개체의 표현을으로 문자열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-246">The example in this document uses strings as representations of provided objects.</span></span> <span data-ttu-id="4e722-247">대부분의 경우 표현에 대 한 다른 개체를 사용 하는 적절 한 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-247">Frequently, it may be appropriate to use other objects for representations.</span></span> <span data-ttu-id="4e722-248">예를 들어 속성 모음으로 사전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-248">For example, you may use a dictionary as a property bag:</span></span>

```fsharp
ProvidedConstructor(parameters = [], 
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

<span data-ttu-id="4e722-249">대신 하나 이상의 런타임 작업 함께 표현을를 런타임에 사용 하 여 형식 공급자는 형식을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-249">As an alternative, you may define a type in your type provider that will be used at runtime to form the representation, along with one or more runtime operations:</span></span>

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

<span data-ttu-id="4e722-250">제공 된 멤버 그런 다음이 개체 유형의 인스턴스를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-250">Provided members can then construct instances of this object type:</span></span>

```fsharp
ProvidedConstructor(parameters = [], 
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

<span data-ttu-id="4e722-251">이 경우 (선택 사항) 서 사용할 수 있습니다이 유형은 유형 지우기로이 형식을 지정 하 여는 `baseType` 를 생성할 때는 `ProvidedTypeDefinition`:</span><span class="sxs-lookup"><span data-stu-id="4e722-251">In this case, you may (optionally) use this type as the type erasure by specifying this type as the `baseType` when constructing the `ProvidedTypeDefinition`:</span></span>

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a><span data-ttu-id="4e722-252">주요 결론</span><span class="sxs-lookup"><span data-stu-id="4e722-252">Key Lessons</span></span>

<span data-ttu-id="4e722-253">이전 섹션에는 다양 한 형식, 속성 및 메서드를 제공 하는 간단한 지우기 형식 공급자를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-253">The previous section explained how to create a simple erasing type provider that provides a range of types, properties, and methods.</span></span> <span data-ttu-id="4e722-254">또한이 섹션의 장점 중 일부와 지워진된 형식을 형식 공급자에서 제공 하는 경우의 단점을 포함 하 여 형식 삭제의 개념을 설명 하 고 지워진 형식의 표시를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-254">This section also explained the concept of type erasure, including some of the advantages and disadvantages of providing erased types from a type provider, and discussed representations of erased types.</span></span>


## <a name="a-type-provider-that-uses-static-parameters"></a><span data-ttu-id="4e722-255">정적 매개 변수를 사용 하는 형식 공급자</span><span class="sxs-lookup"><span data-stu-id="4e722-255">A Type Provider That Uses Static Parameters</span></span>

<span data-ttu-id="4e722-256">정적 데이터 여 형식 공급자를 매개 변수화 수 있으므로 경우 공급자는 로컬 또는 원격 데이터에 액세스할 수 필요 하지 않은 경우에 많은 관심 있는 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-256">The ability to parameterize type providers by static data enables many interesting scenarios, even in cases when the provider doesn't need to access any local or remote data.</span></span> <span data-ttu-id="4e722-257">이 섹션에서는 이러한 공급자를 작성 하기 위한 몇 가지 기본 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-257">In this section, you’ll learn some basic techniques for putting together such a provider.</span></span>


### <a name="type-checked-regex-provider"></a><span data-ttu-id="4e722-258">Regex 공급자를 확인 하는 입력</span><span class="sxs-lookup"><span data-stu-id="4e722-258">Type Checked Regex Provider</span></span>

<span data-ttu-id="4e722-259">.NET을 래핑하는 정규식에 대 한 형식 공급자를 구현 하 고 가정 <xref:System.Text.RegularExpressions.Regex> 다음 컴파일 타임 보증을 제공 하는 인터페이스에서 라이브러리:</span><span class="sxs-lookup"><span data-stu-id="4e722-259">Imagine that you want to implement a type provider for regular expressions that wraps the .NET <xref:System.Text.RegularExpressions.Regex> libraries in an interface that provides the following compile-time guarantees:</span></span>

- <span data-ttu-id="4e722-260">정규식 올바른지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-260">Verifying whether a regular expression is valid.</span></span>

- <span data-ttu-id="4e722-261">일치 하는 정규식에서 모든 그룹 이름을 기반으로 하는 항목에 명명 된 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-261">Providing named properties on matches that are based on any group names in the regular expression.</span></span>

<span data-ttu-id="4e722-262">이 섹션에서는 만들려는 형식 공급자를 사용 하는 방법을 보여 줍니다는 `RegexTyped` 정규식 패턴에서 이러한 장점을 제공 하기 위해 매개 변수화를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-262">This section shows you how to use type providers to create a `RegexTyped` type that the regular expression pattern parameterizes to provide these benefits.</span></span> <span data-ttu-id="4e722-263">형식 공급자를 추출할 수 있는 그룹 패턴에서 명명 된 일치 하는 속성을 사용 하 여 액세스할 수 있도록와 지정 된 패턴과 유효 없는 경우 컴파일러에서 오류를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-263">The compiler will report an error if the supplied pattern isn't valid, and the type provider can extract the groups from the pattern so that you can access them by using named properties on matches.</span></span> <span data-ttu-id="4e722-264">형식 공급자를 디자인할 때 노출 된 API 모양 고려해 야 최종 사용자와.NET 코드에이 디자인은 변환 하는 방법에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-264">When you design a type provider, you should consider how its exposed API should look to end users and how this design will translate to .NET code.</span></span> <span data-ttu-id="4e722-265">다음 예제에는 지역 번호의 구성 요소를 이러한 API를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-265">The following example shows how to use such an API to get the components of the area code:</span></span>

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

<span data-ttu-id="4e722-266">다음 예제에서는 형식 공급자에서 이러한 호출을 변환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-266">The following example shows how the type provider translates these calls:</span></span>

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

<span data-ttu-id="4e722-267">다음 사항을 note:</span><span class="sxs-lookup"><span data-stu-id="4e722-267">Note the following points:</span></span>

- <span data-ttu-id="4e722-268">표준 정규식을 나타내는 매개 변수화 된 `RegexTyped` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-268">The standard Regex type represents the parameterized `RegexTyped` type.</span></span>

- <span data-ttu-id="4e722-269">`RegexTyped` 생성자의 패턴에 대 한 정적 형식 인수를 전달 Regex 생성자에 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-269">The `RegexTyped` constructor results in a call to the Regex constructor, passing in the static type argument for the pattern.</span></span>

- <span data-ttu-id="4e722-270">결과 `Match` 표준에 따라 나타내는 메서드에 <xref:System.Text.RegularExpressions.Match> 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-270">The results of the `Match` method are represented by the standard <xref:System.Text.RegularExpressions.Match> type.</span></span>

- <span data-ttu-id="4e722-271">제공 된 속성의 결과 각 명명 된 그룹에 일치 하는 인덱서를 사용 하는 결과 속성에 액세스 및 `Groups` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-271">Each named group results in a provided property, and accessing the property results in a use of an indexer on a match’s `Groups` collection.</span></span>

<span data-ttu-id="4e722-272">다음 코드는 이러한 공급자를 구현 하는 논리의 핵심 하 고이 예에서는 제공 된 형식으로 모든 멤버의 추가 생략 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-272">The following code is the core of the logic to implement such a provider, and this example omits the addition of all members to the provided type.</span></span> <span data-ttu-id="4e722-273">추가 된 각 멤버에 대 한 자세한 내용은이 항목 뒷부분의 적절 한 섹션을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-273">For information about each added member, see the appropriate section later in this topic.</span></span> <span data-ttu-id="4e722-274">전체 코드에서 샘플을 다운로드는 [F # 3.0 샘플 팩](https://fsharp3sample.codeplex.com) Codeplex 웹 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-274">For the full code, download the sample from the [F# 3.0 Sample Pack](https://fsharp3sample.codeplex.com) on the Codeplex website.</span></span>

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams, 
        instantiationFunction=(fun typeName parameterValues ->

          match parameterValues with 
          | [| :? string as pattern|] -> 

            // Create an instance of the regular expression. 
            //
            // This will fail with System.ArgumentException if the regular expression is not valid. 
            // The exception will escape the type provider and be reported in client code.
            let r = System.Text.RegularExpressions.Regex(pattern)            

            // Declare the typed regex provided type.
            // The type erasure of this type is 'obj', even though the representation will always be a Regex
            // This, combined with hiding the object methods, makes the IntelliSense experience simpler.
            let ty = 
              ProvidedTypeDefinition(
                thisAssembly, 
                rootNamespace, 
                typeName, 
                baseType = Some baseTy)

            ...

            ty
          | _ -> failwith "unexpected parameter values")) 

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

<span data-ttu-id="4e722-275">다음 사항을 note:</span><span class="sxs-lookup"><span data-stu-id="4e722-275">Note the following points:</span></span>

- <span data-ttu-id="4e722-276">형식 공급자는 두 개의 정적 매개 변수:는 `pattern`, 필수 작업이 있는 및 `options`, (기본값을 제공 되기 때문에) 하는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-276">The type provider takes two static parameters: the `pattern`, which is mandatory, and the `options`, which are optional (because a default value is provided).</span></span>

- <span data-ttu-id="4e722-277">정적 인수를 입력 한 후 정규식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-277">After the static arguments are supplied, you create an instance of the regular expression.</span></span> <span data-ttu-id="4e722-278">이 인스턴스의 Regex, 잘못 되었으며 사용자에 게이 오류를 보고 됩니다 하는 경우 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-278">This instance will throw an exception if the Regex is malformed, and this error will be reported to users.</span></span>

- <span data-ttu-id="4e722-279">내에서 `DefineStaticParameters` 인수가 제공 되는 후 반환 되는 형식을 정의 콜백에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-279">Within the `DefineStaticParameters` callback, you define the type that will be returned after the arguments are supplied.</span></span>

- <span data-ttu-id="4e722-280">이 코드 설정 `HideObjectMethods` true 간소화 된 IntelliSense 환경을 계속 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-280">This code sets `HideObjectMethods` to true so that the IntelliSense experience will remain streamlined.</span></span> <span data-ttu-id="4e722-281">이 특성을 사용 하면는 `Equals`, `GetHashCode`, `Finalize`, 및 `GetType` 멤버 억제 하도록 제공 된 개체에 대 한 IntelliSense 목록에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-281">This attribute causes the `Equals`, `GetHashCode`, `Finalize`, and `GetType` members to be suppressed from IntelliSense lists for a provided object.</span></span>

- <span data-ttu-id="4e722-282">사용 하면 `obj` 수 있지만 메서드를의 기본 유형을 사용 하 여 대로 `Regex` 개체는 다음 예제와 같이이 형식의 런타임 표현이으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-282">You use `obj` as the base type of the method, but you’ll use a `Regex` object as the runtime representation of this type, as the next example shows.</span></span>

- <span data-ttu-id="4e722-283">에 대 한 호출의 `Regex` 생성자 throw는 <xref:System.ArgumentException> 경우 정규식 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-283">The call to the `Regex` constructor throws a <xref:System.ArgumentException> when a regular expression isn’t valid.</span></span> <span data-ttu-id="4e722-284">컴파일러는이 예외를 catch 하 고 컴파일 타임에 또는 Visual Studio 편집기에서 오류 메시지를 사용자에 게 보고.</span><span class="sxs-lookup"><span data-stu-id="4e722-284">The compiler catches this exception and reports an error message to the user at compile time or in the Visual Studio editor.</span></span> <span data-ttu-id="4e722-285">이 예외를 응용 프로그램을 실행 하지 않고 유효성을 검사 하려면 정규식 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-285">This exception enables regular expressions to be validated without running an application.</span></span>

<span data-ttu-id="4e722-286">위에 정의 된 형식 도움이 되지 않습니다 아직 의미 있는 메서드 또는 속성을 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-286">The type defined above isn't useful yet because it doesn’t contain any meaningful methods or properties.</span></span> <span data-ttu-id="4e722-287">먼저 추가 하는 정적 `IsMatch` 메서드:</span><span class="sxs-lookup"><span data-stu-id="4e722-287">First, add a static `IsMatch` method:</span></span>

```fsharp
let isMatch = 
    ProvidedMethod(
        methodName = "IsMatch", 
        parameters = [ProvidedParameter("input", typeof<string>)], 
        returnType = typeof<bool>, 
        isStatic = true,
        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>) 

isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string." 
ty.AddMember isMatch
```

<span data-ttu-id="4e722-288">앞의 코드는 메서드를 정의 `IsMatch`, 입력으로 문자열을 반환 하는 `bool`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-288">The previous code defines a method `IsMatch`, which takes a string as input and returns a `bool`.</span></span> <span data-ttu-id="4e722-289">사용 하는 것만 문제가 되는 부분은 `args` 내에서 인수는 `InvokeCode` 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-289">The only tricky part is the use of the `args` argument within the `InvokeCode` definition.</span></span> <span data-ttu-id="4e722-290">이 예제에서는 `args` 이 메서드를 인수를 나타내는 인용구의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-290">In this example, `args` is a list of quotations that represents the arguments to this method.</span></span> <span data-ttu-id="4e722-291">첫 번째 인수를 나타내는 메서드가 인스턴스 메서드인 경우는 `this` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-291">If the method is an instance method, the first argument represents the `this` argument.</span></span> <span data-ttu-id="4e722-292">그러나 정적 메서드에 대 한 인수는 메서드에 명시적 인수가 모두.</span><span class="sxs-lookup"><span data-stu-id="4e722-292">However, for a static method, the arguments are all just the explicit arguments to the method.</span></span> <span data-ttu-id="4e722-293">따옴표 붙은 값의 형식을 지정 된 반환 형식이 일치 해야 함을 참고 (이 경우 `bool`).</span><span class="sxs-lookup"><span data-stu-id="4e722-293">Note that the type of the quoted value should match the specified return type (in this case, `bool`).</span></span> <span data-ttu-id="4e722-294">또한이 코드를 사용 하는 참고는 `AddXmlDoc` 메서드를 제공 된 메서드에도 유용한 설명서를 IntelliSense를 통해 제공할 수 있습니다에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-294">Also note that this code uses the `AddXmlDoc` method to make sure that the provided method also has useful documentation, which you can supply through IntelliSense.</span></span>

<span data-ttu-id="4e722-295">다음에 인스턴스 Match 메서드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-295">Next, add an instance Match method.</span></span> <span data-ttu-id="4e722-296">하지만이 메서드는 제공 된 값을 반환 해야 `Match` 을 입력 하 여 그룹에 강력한 형식의 적절 하 게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-296">However, this method should return a value of a provided `Match` type so that the groups can be accessed in a strongly typed fashion.</span></span> <span data-ttu-id="4e722-297">먼저 선언 따라서는 `Match` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-297">Thus, you first declare the `Match` type.</span></span> <span data-ttu-id="4e722-298">이 형식은 정적 인수로 제공 된 패턴에 의존 하기 때문에이 형식 매개 변수가 있는 형식 정의 내에서 중첩 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-298">Because this type depends on the pattern that was supplied as a static argument, this type must be nested within the parameterized type definition:</span></span>

```fsharp
let matchTy = 
    ProvidedTypeDefinition(
        "MatchType", 
        baseType = Some baseTy, 
        hideObjectMethods = true)

ty.AddMember matchTy
```

<span data-ttu-id="4e722-299">다음 각 그룹에 대해 일치 하는 항목 형식에 하나의 속성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-299">You then add one property to the Match type for each group.</span></span> <span data-ttu-id="4e722-300">런타임 시 일치 하는로 표시 되는 <xref:System.Text.RegularExpressions.Match> 값 이므로 속성을 정의 하는 인용 사용 해야 합니다는 <xref:System.Text.RegularExpressions.Match.Groups> 인덱싱된 관련 그룹을 가져올 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-300">At runtime, a match is represented as a <xref:System.Text.RegularExpressions.Match> value, so the quotation that defines the property must use the <xref:System.Text.RegularExpressions.Match.Groups> indexed property to get the relevant group.</span></span>

```fsharp
for group in r.GetGroupNames() do
    // Ignore the group named 0, which represents all input.
    if group <> "0" then
    let prop = 
      ProvidedProperty(
        propertyName = group, 
        propertyType = typeof<Group>, 
        getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
    matchTy.AddMember prop
```

<span data-ttu-id="4e722-301">제공된 된 속성을 XML 문서를 추가 하는 참고 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-301">Again, note that you’re adding XML documentation to the provided property.</span></span> <span data-ttu-id="4e722-302">또한 경우 속성을 읽을 수 있는 참고는 `GetterCode` 함수를 제공 하 고 하는 경우 속성을 쓸 수는 `SetterCode` 함수가 제공 되어 결과 속성은 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-302">Also note that a property can be read if a `GetterCode` function is provided, and the property can be written if a `SetterCode` function is provided, so the resulting property is read only.</span></span>

<span data-ttu-id="4e722-303">이 값을 반환 하는 인스턴스 메서드를 만들 수 이제 `Match` 유형:</span><span class="sxs-lookup"><span data-stu-id="4e722-303">Now you can create an instance method that returns a value of this `Match` type:</span></span>

```fsharp
let matchMethod = 
    ProvidedMethod(
        methodName = "Match", 
        parameters = [ProvidedParameter("input", typeof<string>)], 
        returnType = matchTy, 
        invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)

matchMeth.AddXmlDoc "Searches the specified input string for the first ocurrence of this regular expression" 

ty.AddMember matchMeth
```

<span data-ttu-id="4e722-304">인스턴스 메서드를 작성 하는 `args.[0]` 나타냅니다는 `RegexTyped` 에 메서드가 호출 되 고, 인스턴스 및 `args.[1]` 입력 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-304">Because you are creating an instance method, `args.[0]` represents the `RegexTyped` instance on which the method is being called, and `args.[1]` is the input argument.</span></span>

<span data-ttu-id="4e722-305">마지막으로 제공 된 형식의 인스턴스를 만들 수 있도록 하는 생성자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-305">Finally, provide a constructor so that instances of the provided type can be created.</span></span>

```fsharp
let ctor = 
    ProvidedConstructor(
        parameters = [], 
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

<span data-ttu-id="4e722-306">생성자 이므로 다시 boxed 개체에는 표준.NET Regex 인스턴스를 만드는 것에 단순히 지웁니다 `obj` 제공 된 형식이 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-306">The constructor merely erases to the creation of a standard .NET Regex instance, which is again boxed to an object because `obj` is the erasure of the provided type.</span></span> <span data-ttu-id="4e722-307">변경 하는 항목의 앞부분에서 지정한 API 사용법 예제 예상 대로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-307">With that change, the sample API usage that specified earlier in the topic works as expected.</span></span> <span data-ttu-id="4e722-308">다음 코드는 완전 하 고 최종:</span><span class="sxs-lookup"><span data-stu-id="4e722-308">The following code is complete and final:</span></span>

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types.
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams, 
        instantiationFunction=(fun typeName parameterValues ->

            match parameterValues with 
            | [| :? string as pattern|] -> 

                // Create an instance of the regular expression. 

                let r = System.Text.RegularExpressions.Regex(pattern)            

                // Declare the typed regex provided type.

                let ty = 
                    ProvidedTypeDefinition(
                        thisAssembly, 
                        rootNamespace, 
                        typeName, 
                        baseType = Some baseTy)

                ty.AddXmlDoc "A strongly typed interface to the regular expression '%s'"

                // Provide strongly typed version of Regex.IsMatch static method.
                let isMatch = 
                    ProvidedMethod(
                        methodName = "IsMatch", 
                        parameters = [ProvidedParameter("input", typeof<string>)], 
                        returnType = typeof<bool>, 
                        isStatic = true,
                        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>) 

                isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string"

                ty.AddMember isMatch

                // Provided type for matches
                // Again, erase to obj even though the representation will always be a Match
                let matchTy = 
                    ProvidedTypeDefinition(
                        "MatchType", 
                        baseType = Some baseTy, 
                        hideObjectMethods = true)

                // Nest the match type within parameterized Regex type.
                ty.AddMember matchTy

                // Add group properties to match type
                for group in r.GetGroupNames() do
                    // Ignore the group named 0, which represents all input.
                    if group <> "0" then
                        let prop = 
                          ProvidedProperty(
                            propertyName = group, 
                            propertyType = typeof<Group>, 
                            getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
                        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
                        matchTy.AddMember(prop)

                // Provide strongly typed version of Regex.Match instance method.
                let matchMeth = 
                  ProvidedMethod(
                    methodName = "Match", 
                    parameters = [ProvidedParameter("input", typeof<string>)], 
                    returnType = matchTy, 
                    invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)
                matchMeth.AddXmlDoc "Searches the specified input string for the first occurence of this regular expression"

                ty.AddMember matchMeth

                // Declare a constructor.
                let ctor = 
                  ProvidedConstructor(
                    parameters = [], 
                    invokeCode = fun args -> <@@ Regex(pattern) :> obj @@>)

                // Add documentation to the constructor.
                ctor.AddXmlDoc "Initializes a regular expression instance"

                ty.AddMember ctor

                ty
            | _ -> failwith "unexpected parameter values")) 

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

### <a name="key-lessons"></a><span data-ttu-id="4e722-309">주요 결론</span><span class="sxs-lookup"><span data-stu-id="4e722-309">Key Lessons</span></span>

<span data-ttu-id="4e722-310">이 섹션에는 정적 매개 변수에서 작동 하는 형식 공급자를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-310">This section explained how to create a type provider that operates on its static parameters.</span></span> <span data-ttu-id="4e722-311">공급자는 static 매개 변수를 확인 하 고 해당 값에 따라 작업을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-311">The provider checks the static parameter and provides operations based on its value.</span></span>


## <a name="a-type-provider-that-is-backed-by-local-data"></a><span data-ttu-id="4e722-312">로컬 데이터에서 지 원하는 형식 공급자</span><span class="sxs-lookup"><span data-stu-id="4e722-312">A Type Provider That Is Backed By Local Data</span></span>

<span data-ttu-id="4e722-313">자주 형식 공급자 Api를 기반으로 정적 매개 변수 뿐만 아니라 로컬 또는 원격 시스템에서 정보를 표시 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-313">Frequently you might want type providers to present APIs based on not only static parameters but also information from local or remote systems.</span></span> <span data-ttu-id="4e722-314">이 섹션에서는 로컬 데이터 파일과 같은 로컬 데이터를 기반으로 하는 형식 공급자에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-314">This section discusses type providers that are based on local data, such as local data files.</span></span>


### <a name="simple-csv-file-provider"></a><span data-ttu-id="4e722-315">간단한 CSV 파일 공급자</span><span class="sxs-lookup"><span data-stu-id="4e722-315">Simple CSV File Provider</span></span>

<span data-ttu-id="4e722-316">간단한 예로 공학용 형식으로 데이터를 쉼표로 구분 된 값 (CSV)에 액세스 하기 위한 형식 공급자를 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-316">As a simple example, consider a type provider for accessing scientific data in Comma Separated Value (CSV) format.</span></span> <span data-ttu-id="4e722-317">이 섹션에서는 CSV 파일 다음 표에서 같이 뒤에 부동 소수점 데이터는 머리글 행을 포함 하는 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-317">This section assumes that the CSV files contain a header row followed by floating point data, as the following table illustrates:</span></span>


|<span data-ttu-id="4e722-318">거리 (미터)</span><span class="sxs-lookup"><span data-stu-id="4e722-318">Distance (meter)</span></span>|<span data-ttu-id="4e722-319">시간 (초)</span><span class="sxs-lookup"><span data-stu-id="4e722-319">Time (second)</span></span>|
|----------------|-------------|
|<span data-ttu-id="4e722-320">50.0</span><span class="sxs-lookup"><span data-stu-id="4e722-320">50.0</span></span>|<span data-ttu-id="4e722-321">3.7</span><span class="sxs-lookup"><span data-stu-id="4e722-321">3.7</span></span>|
|<span data-ttu-id="4e722-322">100.0</span><span class="sxs-lookup"><span data-stu-id="4e722-322">100.0</span></span>|<span data-ttu-id="4e722-323">5.2</span><span class="sxs-lookup"><span data-stu-id="4e722-323">5.2</span></span>|
|<span data-ttu-id="4e722-324">150.0</span><span class="sxs-lookup"><span data-stu-id="4e722-324">150.0</span></span>|<span data-ttu-id="4e722-325">6.4</span><span class="sxs-lookup"><span data-stu-id="4e722-325">6.4</span></span>|

<span data-ttu-id="4e722-326">이 섹션에 있는 행을 가져오는 데 사용할 수 있는 형식을 제공 하는 방법을 보여 줍니다는 `Distance` 형식의 속성이 `float<meter>` 및 `Time` 형식의 속성이 `float<second>`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-326">This section shows how to provide a type that you can use to get rows with a `Distance` property of type `float<meter>` and a `Time` property of type `float<second>`.</span></span> <span data-ttu-id="4e722-327">간단히 하기 위해 다음과 같은 가정 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-327">For simplicity, the following assumptions are made:</span></span>

- <span data-ttu-id="4e722-328">헤더 이름이 단위가 또는 "(단위) 이름" 형식으로 되어 및 쉼표를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-328">Header names are either unit-less or have the form "Name (unit)" and don't contain commas.</span></span>

- <span data-ttu-id="4e722-329">단위는으로 모두 사용 하 International (SI) 단위는 [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames 모듈 (F #)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) 모듈을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-329">Units are all Systeme International (SI) units as the [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames Module (F#)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) module defines.</span></span>

- <span data-ttu-id="4e722-330">단위는 모두 간단한 (예를 들어 미터링) 복합 (예를 들어, 미터 수/초) 보다는 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-330">Units are all simple (for example, meter) rather than compound (for example, meter/second).</span></span>

- <span data-ttu-id="4e722-331">모든 열에 부동 소수점 데이터 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-331">All columns contain floating point data.</span></span>

<span data-ttu-id="4e722-332">보다 완전 공급자는 이러한 제한 사항은 풉니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-332">A more complete provider would loosen these restrictions.</span></span>

<span data-ttu-id="4e722-333">다시 API 모양 고려해 야 하는 첫 번째 단계가입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-333">Again the first step is to consider how the API should look.</span></span> <span data-ttu-id="4e722-334">이전 테이블의 콘텐츠(쉼표로 분리된 형식)를 사용하여 `info.csv` 파일을 지정한 경우 공급자의 사용자는 다음 예제와 비슷한 코드를 작성할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-334">Given an `info.csv` file with the contents from the previous table (in comma-separated format), users of the provider should be able to write code that resembles the following example:</span></span>

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

<span data-ttu-id="4e722-335">이 경우 컴파일러는 다음 예제와 같은 것으로 이러한 호출을 변환 해야:</span><span class="sxs-lookup"><span data-stu-id="4e722-335">In this case, the compiler should convert these calls into something like the following example:</span></span>

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

<span data-ttu-id="4e722-336">최적의 번역 실제를 정의 하는 형식 공급자 내용의 `CsvFile` 형식 공급자 어셈블리의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-336">The optimal translation will require the type provider to define a real `CsvFile` type in the type provider's assembly.</span></span> <span data-ttu-id="4e722-337">형식 공급자는 종종 몇 가지 도우미 형식 및 메서드를 중요 한 논리를 래핑하에 의존 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-337">Type providers often rely on a few helper types and methods to wrap important logic.</span></span> <span data-ttu-id="4e722-338">측정값은 런타임 시 지워지거나, 하므로 사용할 수 있습니다는 `float[]` 행에 대 한 지워진 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-338">Because measures are erased at runtime, you can use a `float[]` as the erased type for a row.</span></span> <span data-ttu-id="4e722-339">컴파일러는 서로 다른 측정값 형식으로 서로 다른 열을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-339">The compiler will treat different columns as having different measure types.</span></span> <span data-ttu-id="4e722-340">예를 들어 예에서 첫 번째 열은 형식이 `float<meter>`, 있고 두 번째 `float<second>`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-340">For example, the first column in our example has type `float<meter>`, and the second has `float<second>`.</span></span> <span data-ttu-id="4e722-341">그러나 지워진된 표현 남아 있을 수 있는 방법은 매우 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-341">However, the erased representation can remain quite simple.</span></span>

<span data-ttu-id="4e722-342">다음 코드에서는 구현 코어를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-342">The following code shows the core of the implementation.</span></span>

```fsharp
// Simple type wrapping CSV data
type CsvFile(filename) =
    // Cache the sequence of all data lines (all lines but the first)
    let data = 
        seq { for line in File.ReadAllLines(filename) |> Seq.skip 1 do
                 yield line.Split(',') |> Array.map float }
        |> Seq.cache
    member __.Data = data

[<TypeProvider>]
type public MiniCsvProvider(cfg:TypeProviderConfig) as this =
    inherit TypeProviderForNamespaces(cfg)

    // Get the assembly and namespace used to house the provided types.
    let asm = System.Reflection.Assembly.GetExecutingAssembly()
    let ns = "Samples.FSharp.MiniCsvProvider"

    // Create the main provided type.
    let csvTy = ProvidedTypeDefinition(asm, ns, "MiniCsv", Some(typeof<obj>))

    // Parameterize the type by the file to use as a template.
    let filename = ProvidedStaticParameter("filename", typeof<string>)
    do csvTy.DefineStaticParameters([filename], fun tyName [| :? string as filename |] ->
    
        // Resolve the filename relative to the resolution folder.
        let resolvedFilename = Path.Combine(cfg.ResolutionFolder, filename)

        // Get the first line from the file.
        let headerLine = File.ReadLines(resolvedFilename) |> Seq.head

        // Define a provided type for each row, erasing to a float[].
        let rowTy = ProvidedTypeDefinition("Row", Some(typeof<float[]>))

        // Extract header names from the file, splitting on commas.
        // use Regex matching to get the position in the row at which the field occurs
        let headers = Regex.Matches(headerLine, "[^,]+")

        // Add one property per CSV field.
        for i in 0 .. headers.Count - 1 do
            let headerText = headers.[i].Value

            // Try to decompose this header into a name and unit.
            let fieldName, fieldTy =
                let m = Regex.Match(headerText, @"(?<field>.+) \((?<unit>.+)\)")
                if m.Success then

                    let unitName = m.Groups.["unit"].Value
                    let units = ProvidedMeasureBuilder.Default.SI unitName
                    m.Groups.["field"].Value, ProvidedMeasureBuilder.Default.AnnotateType(typeof<float>,[units])

                else
                    // no units, just treat it as a normal float
                    headerText, typeof<float>

            let prop = 
                ProvidedProperty(fieldName, fieldTy, 
                    getterCode = fun [row] -> <@@ (%%row:float[]).[i] @@>)

            // Add metadata that defines the property's location in the referenced file.
            prop.AddDefinitionLocation(1, headers.[i].Index + 1, filename)
            rowTy.AddMember(prop) 

        // Define the provided type, erasing to CsvFile.
        let ty = ProvidedTypeDefinition(asm, ns, tyName, Some(typeof<CsvFile>))

        // Add a parameterless constructor that loads the file that was used to define the schema.
        let ctor0 = 
            ProvidedConstructor([], 
                invokeCode = fun [] -> <@@ CsvFile(resolvedFilename) @@>)
        ty.AddMember ctor0

        // Add a constructor that takes the file name to load.
        let ctor1 = ProvidedConstructor([ProvidedParameter("filename", typeof<string>)], 
            invokeCode = fun [filename] -> <@@ CsvFile(%%filename) @@>)
        ty.AddMember ctor1

        // Add a more strongly typed Data property, which uses the existing property at runtime.
        let prop = 
            ProvidedProperty("Data", typedefof<seq<_>>.MakeGenericType(rowTy), 
                getterCode = fun [csvFile] -> <@@ (%%csvFile:CsvFile).Data @@>)
        ty.AddMember prop

        // Add the row type as a nested type.
        ty.AddMember rowTy
        ty)

    // Add the type to the namespace.
    do this.AddNamespace(ns, [csvTy])
```

<span data-ttu-id="4e722-343">Note는 구현에 대 한 다음과 같은 사항:</span><span class="sxs-lookup"><span data-stu-id="4e722-343">Note the following points about the implementation:</span></span>

- <span data-ttu-id="4e722-344">오버 로드 된 생성자에는 원본 파일 또는 읽어야 하는 동일한 스키마가 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-344">Overloaded constructors allow either the original file or one that has an identical schema to be read.</span></span> <span data-ttu-id="4e722-345">이 패턴 일반적인 경우가 로컬 또는 원격 데이터 원본에 대 한 형식 공급자를 작성 하 고이 패턴에는 로컬 파일에서 원격 데이터에 대 한 템플릿으로 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-345">This pattern is common when you write a type provider for local or remote data sources, and this pattern allows a local file to be used as the template for remote data.</span></span>

- <span data-ttu-id="4e722-346">사용할 수는 [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) 상대 파일 이름을 확인 하기 위해 형식 공급자 생성자에 전달 되는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-346">You can use the [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) value that’s passed in to the type provider constructor to resolve relative file names.</span></span>

- <span data-ttu-id="4e722-347">사용할 수는 `AddDefinitionLocation` 메서드를 제공 되는 속성의 위치를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-347">You can use the `AddDefinitionLocation` method to define the location of the provided properties.</span></span> <span data-ttu-id="4e722-348">따라서 사용 하는 경우 `Go To Definition` 에서 제공 된 속성을 CSV 파일은 Visual Studio에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-348">Therefore, if you use `Go To Definition` on a provided property, the CSV file will open in Visual Studio.</span></span>

- <span data-ttu-id="4e722-349">사용할 수는 `ProvidedMeasureBuilder` SI 단위를 조회 하 고 관련 생성 하도록 형식 `float<_>` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-349">You can use the `ProvidedMeasureBuilder` type to look up the SI units and to generate the relevant `float<_>` types.</span></span>

### <a name="key-lessons"></a><span data-ttu-id="4e722-350">주요 결론</span><span class="sxs-lookup"><span data-stu-id="4e722-350">Key Lessons</span></span>

<span data-ttu-id="4e722-351">이 섹션에는 데이터 원본 자체에 포함 된 간단한 스키마를 로컬 데이터 원본에 대 한 형식 공급자를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-351">This section explained how to create a type provider for a local data source with a simple schema that's contained in the data source itself.</span></span>


## <a name="going-further"></a><span data-ttu-id="4e722-352">계속 진행</span><span class="sxs-lookup"><span data-stu-id="4e722-352">Going Further</span></span>

<span data-ttu-id="4e722-353">다음 섹션에서는 추가 정보에 대 한 제안을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-353">The following sections include suggestions for further study.</span></span>


### <a name="a-look-at-the-compiled-code-for-erased-types"></a><span data-ttu-id="4e722-354">지워진된 형식에 대 한 컴파일된 코드를 살펴보면</span><span class="sxs-lookup"><span data-stu-id="4e722-354">A Look at the Compiled Code for Erased Types</span></span>

<span data-ttu-id="4e722-355">형식 공급자의 사용 하 여 발생 되는 코드에 해당 하는 방법의 몇 가지 아이디어를 제공 하는 다음 함수에서 사용 하 여 조회는 `HelloWorldTypeProvider` 이 항목의 앞부분에 사용 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-355">To give you some idea of how the use of the type provider corresponds to the code that's emitted, look at the following function by using the `HelloWorldTypeProvider` that's used earlier in this topic.</span></span>

```fsharp
let function1 () = 
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

<span data-ttu-id="4e722-356">Ildasm.exe를 사용 하 여 decompiled 결과 코드의 이미지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-356">Here’s an image of the resulting code decompiled by using ildasm.exe:</span></span>

```
.class public abstract auto ansi sealed Module1
extends [mscorlib]System.Object
{
.custom instance void [FSharp.Core]Microsoft.FSharp.Core.CompilationMappingAtt
ribute::.ctor(valuetype [FSharp.Core]Microsoft.FSharp.Core.SourceConstructFlags)
= ( 01 00 07 00 00 00 00 00 )
.method public static int32  function1() cil managed
{
// Code size       24 (0x18)
.maxstack  3
.locals init ([0] object obj1)
IL_0000:  nop
IL_0001:  ldstr      "some data"
IL_0006:  unbox.any  [mscorlib]System.Object
IL_000b:  stloc.0
IL_000c:  ldloc.0
IL_000d:  call       !!0 [FSharp.Core_2]Microsoft.FSharp.Core.LanguagePrimit
ives/IntrinsicFunctions::UnboxGeneric<string>(object)
IL_0012:  callvirt   instance int32 [mscorlib_3]System.String::get_Length()
IL_0017:  ret
} // end of method Module1::function1

} // end of class Module1
```

<span data-ttu-id="4e722-357">예제 에서처럼 형식의 모든 멘 `Type1` 및 `InstanceProperty` 속성 지워졌습니다, 관련 된 런타임 형식에만 작업을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-357">As the example shows, all mentions of the type `Type1` and the `InstanceProperty` property have been erased, leaving only operations on the runtime types involved.</span></span>


### <a name="design-and-naming-conventions-for-type-providers"></a><span data-ttu-id="4e722-358">디자인 및 형식 공급자에 대 한 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="4e722-358">Design and Naming Conventions for Type Providers</span></span>
<span data-ttu-id="4e722-359">형식 공급자를 작성할 때 다음과 같은 규칙을 관찰 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-359">Observe the following conventions when authoring type providers.</span></span>

<span data-ttu-id="4e722-360">**연결 프로토콜에 대 한 공급자** OData 또는 SQL 연결과 같이 데이터 및 서비스 연결 프로토콜에 대 한 대부분 공급자 Dll의 이름은 일반적으로 종료 해야 `TypeProvider` 또는 `TypeProviders`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-360">**Providers for Connectivity Protocols** In general, names of most provider DLLs for data and service connectivity protocols, such as OData or SQL connections, should end in `TypeProvider` or `TypeProviders`.</span></span> <span data-ttu-id="4e722-361">예를 들어 다음 문자열 유사한 DLL 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-361">For example, use a DLL name that resembles the following string:</span></span>

```
  Fabrikam.Management.BasicTypeProviders.dll
```

<span data-ttu-id="4e722-362">제공 된 형식을 해당 네임 스페이스의 멤버 이며 구현 된 연결 프로토콜을 나타내는 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-362">Ensure that your provided types are members of the corresponding namespace, and indicate the connectivity protocol that you implemented:</span></span>

```
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

<span data-ttu-id="4e722-363">**일반적인 코딩 하기 위한 유틸리티 공급자**합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-363">**Utility Providers for General Coding**.</span></span>  <span data-ttu-id="4e722-364">형식 공급자 유틸리티 형식 공급자와 같이 정규식에 대 한 경우 다음 예제와 같이 기본 라이브러리의 일부를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-364">For a utility type provider such as that for regular expressions, the type provider may be part of a base library, as the following example shows:</span></span>

```fsharp
  #r "Fabrikam.Core.Text.Utilities.dll"
```

<span data-ttu-id="4e722-365">이 경우 기본.NET 디자인 규칙에 따라 적절 한 시점에 제공 된 형식 표시:</span><span class="sxs-lookup"><span data-stu-id="4e722-365">In this case, the provided type would appear at an appropriate point according to normal .NET design conventions:</span></span>

```fsharp
  open Fabrikam.Core.Text.RegexTyped
  
  let regex = new RegexTyped<"a+b+a+b+">()
```

<span data-ttu-id="4e722-366">**단일 데이터 원본**합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-366">**Singleton Data Sources**.</span></span> <span data-ttu-id="4e722-367">일부 형식 공급자는 단일 전용된 데이터 원본에 연결 하 고만 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-367">Some type providers connect to a single dedicated data source and provide only data.</span></span> <span data-ttu-id="4e722-368">이 경우 삭제 해야는 `TypeProvider` 접미사 및.NET 명명에 대 한 일반 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-368">In this case, you should drop the `TypeProvider` suffix and use normal conventions for .NET naming:</span></span>

```fsharp
#r "Fabrikam.Data.Freebase.dll"
  
let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

<span data-ttu-id="4e722-369">자세한 내용은 참조는 `GetConnection` 이 항목의 뒷부분에 설명 된 규칙을 디자인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-369">For more information, see the `GetConnection` design convention that's described later in this topic.</span></span>


### <a name="design-patterns-for-type-providers"></a><span data-ttu-id="4e722-370">형식 공급자에 대 한 디자인 패턴</span><span class="sxs-lookup"><span data-stu-id="4e722-370">Design Patterns for Type Providers</span></span>

<span data-ttu-id="4e722-371">다음 섹션에서는 형식 공급자를 작성할 때 사용할 수 있는 디자인 패턴에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-371">The following sections describe design patterns you can use when authoring type providers.</span></span>


#### <a name="the-getconnection-design-pattern"></a><span data-ttu-id="4e722-372">GetConnection 디자인 패턴</span><span class="sxs-lookup"><span data-stu-id="4e722-372">The GetConnection Design Pattern</span></span>
<span data-ttu-id="4e722-373">대부분 형식 공급자를 사용 하도록 작성 해야는 `GetConnection` 다음 예제와 같이 FSharp.Data.TypeProviders.dll에서 형식 공급자에서 사용 되는 패턴:</span><span class="sxs-lookup"><span data-stu-id="4e722-373">Most type providers should be written to use the `GetConnection` pattern that's used by the type providers in FSharp.Data.TypeProviders.dll, as the following example shows:</span></span>

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a><span data-ttu-id="4e722-374">원격 데이터 및 서비스에서 지 원하는 형식 공급자</span><span class="sxs-lookup"><span data-stu-id="4e722-374">Type Providers Backed By Remote Data and Services</span></span>

<span data-ttu-id="4e722-375">원격 데이터 및 서비스에서 지 원하는 형식 공급자를 만들기 전에 다양 한 연결 된 프로그래밍에 내재 된 문제를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-375">Before you create a type provider that's backed by remote data and services, you must consider a range of issues that are inherent in connected programming.</span></span> <span data-ttu-id="4e722-376">이러한 문제는 다음 고려 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-376">These issues include the following considerations:</span></span>

- <span data-ttu-id="4e722-377">스키마 매핑</span><span class="sxs-lookup"><span data-stu-id="4e722-377">schema mapping</span></span>

- <span data-ttu-id="4e722-378">liveness 및 무효화 스키마 변경이 발생할 때</span><span class="sxs-lookup"><span data-stu-id="4e722-378">liveness and invalidation in the presence of schema change</span></span>

- <span data-ttu-id="4e722-379">스키마 캐싱</span><span class="sxs-lookup"><span data-stu-id="4e722-379">schema caching</span></span>

- <span data-ttu-id="4e722-380">데이터 액세스 작업의 비동기 구현</span><span class="sxs-lookup"><span data-stu-id="4e722-380">asynchronous implementations of data access operations</span></span>

- <span data-ttu-id="4e722-381">LINQ 쿼리를 포함 하 여 쿼리를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-381">supporting queries, including LINQ queries</span></span>

- <span data-ttu-id="4e722-382">자격 증명 및 인증</span><span class="sxs-lookup"><span data-stu-id="4e722-382">credentials and authentication</span></span>

<span data-ttu-id="4e722-383">이 항목에는 이러한 문제를 추가로 탐색 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-383">This topic doesn't explore these issues further.</span></span>

### <a name="additional-authoring-techniques"></a><span data-ttu-id="4e722-384">추가 제작 방법</span><span class="sxs-lookup"><span data-stu-id="4e722-384">Additional Authoring Techniques</span></span>

<span data-ttu-id="4e722-385">사용자 고유의 형식 공급자를 작성 하는 경우에 다음과 같은 추가 기술을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-385">When you write your own type providers, you might want to use the following additional techniques.</span></span>

### <a name="creating-types-and-members-on-demand"></a><span data-ttu-id="4e722-386">형식 및 멤버 주문형으로 만들기</span><span class="sxs-lookup"><span data-stu-id="4e722-386">Creating Types and Members On-Demand</span></span>

<span data-ttu-id="4e722-387">ProvidedType API 버전 AddMember의 연기 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-387">The ProvidedType API has delayed versions of AddMember.</span></span>

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

<span data-ttu-id="4e722-388">이러한 버전 형식의 주문형으로 공간을 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-388">These versions are used to create on-demand spaces of types.</span></span>

### <a name="providing-array-types-and-generic-type-instantiations"></a><span data-ttu-id="4e722-389">배열 형식 및 제네릭 형식 인스턴스화를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-389">Providing Array types and Generic Type Instantiations</span></span>

<span data-ttu-id="4e722-390">일반을 사용 하 여 제공 된 멤버 (시그니처 배열 형식, byref 형식 및 제네릭 형식의 인스턴스화에 포함)를 수행한 `MakeArrayType`, `MakePointerType`, 및 `MakeGenericType` 의 모든 인스턴스에서 <xref:System.Type>를 포함 하 여 `ProvidedTypeDefinitions`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-390">You make provided members (whose signatures include array types, byref types, and instantiations of generic types) by using the normal `MakeArrayType`, `MakePointerType`, and `MakeGenericType` on any instance of <xref:System.Type>, including `ProvidedTypeDefinitions`.</span></span>

> [!NOTE]
> <span data-ttu-id="4e722-391">도우미를 사용 해야 경우에 따라 `ProvidedTypeBuilder.MakeGenericType`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-391">In some cases you may have to use the helper in `ProvidedTypeBuilder.MakeGenericType`.</span></span>  <span data-ttu-id="4e722-392">참조는 [형식 공급자 SDK 설명서](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) 내용을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-392">See the [Type Provider SDK documentation](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) for more details.</span></span>

### <a name="providing-unit-of-measure-annotations"></a><span data-ttu-id="4e722-393">주석 측정 단위를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-393">Providing Unit of Measure Annotations</span></span>

<span data-ttu-id="4e722-394">ProvidedTypes API 측정값 주석을 제공 하기 위한 도우미를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-394">The ProvidedTypes API provides helpers for providing measure annotations.</span></span> <span data-ttu-id="4e722-395">형식을 제공 하기 위해 `float<kg>`, 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-395">For example, to provide the type `float<kg>`, use the following code:</span></span>

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  <span data-ttu-id="4e722-396">형식을 제공할 `Nullable<decimal<kg/m^2>>`, 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-396">To provide the type `Nullable<decimal<kg/m^2>>`, use the following code:</span></span>

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a><span data-ttu-id="4e722-397">프로젝트 로컬 이나 스크립트 로컬 리소스에 액세스</span><span class="sxs-lookup"><span data-stu-id="4e722-397">Accessing Project-Local or Script-Local Resources</span></span>

<span data-ttu-id="4e722-398">형식 공급자의 각 인스턴스를 지정할 수는 `TypeProviderConfig` 생성 하는 동안 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-398">Each instance of a type provider can be given a `TypeProviderConfig` value during construction.</span></span> <span data-ttu-id="4e722-399">이 값은 공급자 (즉, 컴파일 또는 스크립트를 포함 하는 디렉터리에 대 한 프로젝트 폴더), 참조 된 어셈블리의 목록 및 기타 정보에 대 한 "해상도 폴더"를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-399">This value contains the "resolution folder" for the provider (that is, the project folder for the compilation or the directory that contains a script), the list of referenced assemblies, and other information.</span></span>

### <a name="invalidation"></a><span data-ttu-id="4e722-400">무효화</span><span class="sxs-lookup"><span data-stu-id="4e722-400">Invalidation</span></span>

<span data-ttu-id="4e722-401">공급자는 F # 언어 서비스 스키마를 가정 하는 변경 된에 알리기 위해 무효화 신호를 발생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-401">Providers can raise invalidation signals to notify the F# language service that the schema assumptions may have changed.</span></span> <span data-ttu-id="4e722-402">무효화 되는 경우 공급자는 Visual Studio에서 호스트 되는 경우는 한 번 다시 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-402">When invalidation occurs, a typecheck is redone if the provider is being hosted in Visual Studio.</span></span> <span data-ttu-id="4e722-403">이 신호 공급자는 F # Interactive에서 또는 F # 컴파일러 (fsc.exe)에 의해 호스팅되는 경우 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-403">This signal will be ignored when the provider is hosted in F# Interactive or by the F# Compiler (fsc.exe).</span></span>

### <a name="caching-schema-information"></a><span data-ttu-id="4e722-404">캐싱 스키마 정보</span><span class="sxs-lookup"><span data-stu-id="4e722-404">Caching Schema Information</span></span>

<span data-ttu-id="4e722-405">공급자는 스키마 정보에 대 한 액세스를 캐시 종종 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-405">Providers must often cache access to schema information.</span></span> <span data-ttu-id="4e722-406">Static 매개 변수 또는 사용자 데이터에 지정 된 파일 이름을 사용 하 여 캐시 된 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-406">The cached data should be stored by using a file name that's given as a static parameter or as user data.</span></span> <span data-ttu-id="4e722-407">스키마 캐시의 예로 `LocalSchemaFile` 에서 형식 공급자에서 매개 변수는 `FSharp.Data.TypeProviders` 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-407">An example of schema caching is the `LocalSchemaFile` parameter in the type providers in the `FSharp.Data.TypeProviders` assembly.</span></span> <span data-ttu-id="4e722-408">이러한 공급자 구현에서이 정적 매개 변수는 데이터 원본 네트워크를 통해 액세스 하는 대신 지정된 된 로컬 파일의 스키마 정보를 사용 하도록 형식 공급자를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-408">In the implementation of these providers, this static parameter directs the type provider to use the schema information in the specified local file instead of accessing the data source over the network.</span></span> <span data-ttu-id="4e722-409">캐시 된 스키마 정보를 사용 하려면 설정 해야 static 매개 변수 `ForceUpdate` 를 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-409">To use cached schema information, you must also set the static parameter `ForceUpdate` to `false`.</span></span> <span data-ttu-id="4e722-410">온라인 및 오프 라인 데이터 액세스를 사용 하는 비슷한 기술을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-410">You could use a similar technique to enable online and offline data access.</span></span>

### <a name="backing-assembly"></a><span data-ttu-id="4e722-411">어셈블리를 백업합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-411">Backing Assembly</span></span>

<span data-ttu-id="4e722-412">컴파일하는 경우는 `.dll` 또는 `.exe` 파일을 백업.dll 파일에 결과 어셈블리에 생성 된 형식을 정적으로 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-412">When you compile a `.dll` or `.exe` file, the backing .dll file for generated types is statically linked into the resulting assembly.</span></span> <span data-ttu-id="4e722-413">이 링크는 해당 최종 어셈블리에 대 한 백업 어셈블리의 중간 언어 (IL) 형식 정 및 관리 되는 모든 리소스를 복사 하 여 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-413">This link is created by copying the Intermediate Language (IL) type definitions and any managed resources from the backing assembly into the final assembly.</span></span> <span data-ttu-id="4e722-414">F # Interactive를 사용 하면 백업.dll 파일 복사 되지 않습니다 하 고 F # Interactive 프로세스에 직접 대신 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-414">When you use F# Interactive, the backing .dll file isn't copied and is instead loaded directly into the F# Interactive process.</span></span>

### <a name="exceptions-and-diagnostics-from-type-providers"></a><span data-ttu-id="4e722-415">예외 및 형식 공급자에서 진단</span><span class="sxs-lookup"><span data-stu-id="4e722-415">Exceptions and Diagnostics from Type Providers</span></span>

<span data-ttu-id="4e722-416">제공 된 형식에서 모든 멤버의 사용 되는 모든 예외를 throw 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-416">All uses of all members from provided types may throw exceptions.</span></span> <span data-ttu-id="4e722-417">모든 경우에는 형식 공급자에서 예외를 throw 하는 경우 호스트 컴파일러 오류를 특성 특정 형식 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-417">In all cases, if a type provider throws an exception, the host compiler attributes the error to a specific type provider.</span></span>

- <span data-ttu-id="4e722-418">내부 컴파일러 오류 예외가 발생 하지 해야 공급자를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-418">Type provider exceptions should never result in internal compiler errors.</span></span>

- <span data-ttu-id="4e722-419">형식 공급자는 경고를 보고할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-419">Type providers can't report warnings.</span></span>

- <span data-ttu-id="4e722-420">형식 공급자는 F # 컴파일러, F # 개발 환경에서 또는 F # Interactive에서 호스트 되는 경우 해당 공급자에서 모든 예외를 발견 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-420">When a type provider is hosted in the F# compiler, an F# development environment, or F# Interactive, all exceptions from that provider are caught.</span></span> <span data-ttu-id="4e722-421">Message 속성은 항상 오류 텍스트를 하 고 스택 추적이 없습니다 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-421">The Message property is always the error text, and no stack trace appears.</span></span> <span data-ttu-id="4e722-422">예외를 throw 하려는 경우 다음 예제에서는 throw 할 수 있습니다: `System.NotSupportedException`, `System.IO.IOException`, `System.Exception`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-422">If you’re going to throw an exception, you can throw the following examples: `System.NotSupportedException`, `System.IO.IOException`, `System.Exception`.</span></span>

#### <a name="providing-generated-types"></a><span data-ttu-id="4e722-423">생성 된 형식 제공</span><span class="sxs-lookup"><span data-stu-id="4e722-423">Providing Generated Types</span></span>

<span data-ttu-id="4e722-424">지금까지이 문서는 지워진된 형식을 제공 하는 방법을 설명 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-424">So far, this document has explained how to provide erased types.</span></span> <span data-ttu-id="4e722-425">사용자의 프로그램에 실제.NET 형식 정의로 추가 되는 생성 된 형식을 제공 하도록 F # 형식 공급자 메커니즘을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-425">You can also use the type provider mechanism in F# to provide generated types, which are added as real .NET type definitions into the users' program.</span></span> <span data-ttu-id="4e722-426">참조 해야 생성 된 형식 정의 사용 하 여 형식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-426">You must refer to generated provided types by using a type definition.</span></span>

```fsharp
open Microsoft.FSharp.TypeProviders 

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

<span data-ttu-id="4e722-427">F # 3.0 버전의 일부인 ProvidedTypes 0.2 도우미 코드에서는 제한적 으로만 생성 된 형식을 제공 하는 데 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-427">The ProvidedTypes-0.2 helper code that is part of the F# 3.0 release has only limited support for providing generated types.</span></span> <span data-ttu-id="4e722-428">다음 문은 생성 된 형식 정의 대해 적용 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-428">The following statements must be true for a generated type definition:</span></span>

- <span data-ttu-id="4e722-429">`isErased` 로 설정 해야 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-429">`isErased` must be set to `false`.</span></span>

- <span data-ttu-id="4e722-430">추가 해야 하는 생성 된 형식에 새로 생성 된 `ProvidedAssembly()`, 생성 된 코드 조각에 대 한 컨테이너를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-430">The generated type must be added to a newly constructed `ProvidedAssembly()`, which represents a container for generated code fragments.</span></span>

- <span data-ttu-id="4e722-431">공급자에서 실제 백업.NET.dll 파일을 디스크에 일치 하는.dll 파일을 가진 어셈블리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-431">The provider must have an assembly that has an actual backing .NET .dll file with a matching .dll file on disk.</span></span>


## <a name="rules-and-limitations"></a><span data-ttu-id="4e722-432">규칙 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="4e722-432">Rules and Limitations</span></span>

<span data-ttu-id="4e722-433">형식 공급자를 작성할 때 다음과 같은 규칙과 제한이 염두에서에 둬야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-433">When you write type providers, keep the following rules and limitations in mind.</span></span>


### <a name="provided-types-must-be-reachable"></a><span data-ttu-id="4e722-434">제공 된 형식을 도달할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-434">Provided types must be reachable</span></span>

<span data-ttu-id="4e722-435">모든 제공 형식을 중첩 되지 않은 형식에서 연결할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-435">All provided types should be reachable from the non-nested types.</span></span> <span data-ttu-id="4e722-436">중첩 되지 않은 형식에 대 한 호출에서 제공 된 `TypeProviderForNamespaces` 호출이 나 생성자 `AddNamespace`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-436">The non-nested types are given in the call to the `TypeProviderForNamespaces` constructor or a call to `AddNamespace`.</span></span> <span data-ttu-id="4e722-437">예를 들어 공급자는 형식을 제공 하는 경우 `StaticClass.P : T`, T는 중첩 되지 않은 형식 또는 아래에 중첩 되어 하나 임을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-437">For example, if the provider provides a type `StaticClass.P : T`, you must ensure that T is either a non-nested type or nested under one.</span></span>

<span data-ttu-id="4e722-438">예를 들어 일부 공급자는 정적 클래스와 같은 `DataTypes` 이러한를 포함 하는 `T1, T2, T3, ...` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-438">For example, some providers have a static class such as `DataTypes` that contain these `T1, T2, T3, ...` types.</span></span> <span data-ttu-id="4e722-439">그렇지 않은 경우 오류 라고 명시 어셈블리 A에에서 형식 T에 대 한 참조를 찾을 수 하지만 해당 어셈블리의 형식을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-439">Otherwise, the error says that a reference to type T in assembly A was found, but the type couldn't be found in that assembly.</span></span> <span data-ttu-id="4e722-440">이 오류가 나타나는 경우에 모든 하위 공급자 형식에서 액세스 될 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-440">If this error appears, verify that all your subtypes can be reached from the provider types.</span></span> <span data-ttu-id="4e722-441">참고: 이러한 `T1, T2, T3...` 종류는 라고 하는 *즉석에서* 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-441">Note: These `T1, T2, T3...` types are referred to as the *on-the-fly* types.</span></span> <span data-ttu-id="4e722-442">액세스할 수 없는 네임 스페이스 또는 부모 형식에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-442">Remember to put them in an accessible namespace or a parent type.</span></span>

### <a name="limitations-of-the-type-provider-mechanism"></a><span data-ttu-id="4e722-443">형식 공급자 메커니즘의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="4e722-443">Limitations of the Type Provider Mechanism</span></span>

<span data-ttu-id="4e722-444">F # 형식 공급자 메커니즘에 다음과 같은 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-444">The type provider mechanism in F# has the following limitations:</span></span>

- <span data-ttu-id="4e722-445">F # 형식 공급자에 대 한 기본 인프라 제네릭 형식 또는 제네릭 메서드를 제공 합니다. 제공을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-445">The underlying infrastructure for type providers in F# doesn't support provided generic types or provided generic methods.</span></span>

- <span data-ttu-id="4e722-446">메커니즘은 정적 매개 변수가 있는 중첩 된 형식을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-446">The mechanism doesn't support nested types with static parameters.</span></span>

## <a name="development-tips"></a><span data-ttu-id="4e722-447">개발 팁</span><span class="sxs-lookup"><span data-stu-id="4e722-447">Development Tips</span></span>

<span data-ttu-id="4e722-448">개발 프로세스 중 다음 팁을 도움이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-448">You might find the following tips helpful during the development process.</span></span>

### <a name="run-two-instances-of-visual-studio"></a><span data-ttu-id="4e722-449">Visual Studio의 두 인스턴스를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-449">Run Two Instances of Visual Studio</span></span>

<span data-ttu-id="4e722-450">한 인스턴스에서 형식 공급자를 개발 하 고 IDE 테스트 형식 공급자를 다시 작성 하지 않도록 하는.dll 파일에 대해 잠금을 수행 하기 때문에 다른 공급자를 테스트 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-450">You can develop the type provider in one instance and test the provider in the other because the test IDE will take a lock on the .dll file that prevents the type provider from being rebuilt.</span></span> <span data-ttu-id="4e722-451">따라서 공급자는 첫 번째 인스턴스에서 만들어지고 공급자 작성 된 후 두 번째 인스턴스를 다시 열 해야 다음 하는 동안 Visual Studio의 두 번째 인스턴스를 닫으십시오.</span><span class="sxs-lookup"><span data-stu-id="4e722-451">Thus, you must close the second instance of Visual Studio while the provider is built in the first instance, and then you must reopen the second instance after the provider is built.</span></span>

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a><span data-ttu-id="4e722-452">형식 공급자 fsc.exe의 호출을 사용 하 여 디버그</span><span class="sxs-lookup"><span data-stu-id="4e722-452">Debug type providers by using invocations of fsc.exe</span></span>

<span data-ttu-id="4e722-453">다음과 같은 도구를 사용 하 여 형식 공급자를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-453">You can invoke type providers by using the following tools:</span></span>

- <span data-ttu-id="4e722-454">fsc.exe (F #은 명령줄 컴파일러)</span><span class="sxs-lookup"><span data-stu-id="4e722-454">fsc.exe (The F# command line compiler)</span></span>

- <span data-ttu-id="4e722-455">fsi.exe (F # Interactive 컴파일러)</span><span class="sxs-lookup"><span data-stu-id="4e722-455">fsi.exe (The F# Interactive compiler)</span></span>

- <span data-ttu-id="4e722-456">devenv.exe (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="4e722-456">devenv.exe (Visual Studio)</span></span>

<span data-ttu-id="4e722-457">종종 fsc.exe 테스트 스크립트 파일 (예를 들어 script.fsx)에서 사용 하 여 형식 공급자를 가장 쉽게 디버깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-457">You can often debug type providers most easily by using fsc.exe on a test script file (for example, script.fsx).</span></span> <span data-ttu-id="4e722-458">명령 프롬프트에서 디버거를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-458">You can launch a debugger from a command prompt.</span></span>

```
  devenv /debugexe fsc.exe script.fsx
```

  <span data-ttu-id="4e722-459">Stdout에 인쇄 로깅을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e722-459">You can use print-to-stdout logging.</span></span>


## <a name="see-also"></a><span data-ttu-id="4e722-460">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e722-460">See Also</span></span>

* [<span data-ttu-id="4e722-461">형식 공급자</span><span class="sxs-lookup"><span data-stu-id="4e722-461">Type Providers</span></span>](index.md)

* [<span data-ttu-id="4e722-462">형식 공급자 SDK</span><span class="sxs-lookup"><span data-stu-id="4e722-462">The Type Provider SDK</span></span>](https://github.com/fsprojects/FSharp.TypeProviders.SDK)

