---
title: "호출자 정보 (F #)"
description: "호출자 정보 인수 특성 메서드에에서 호출자 정보를 사용 하는 방법을 설명 합니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 04/25/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a3dcc335-433b-4672-ac2d-ae6b11b816f3
ms.openlocfilehash: 533d2f0429ddb31e6d1dd7efca2f0760069a2945
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="caller-information"></a><span data-ttu-id="c2639-104">호출자 정보</span><span class="sxs-lookup"><span data-stu-id="c2639-104">Caller information</span></span>

<span data-ttu-id="c2639-105">호출자 정보 특성을 사용하여 메서드 호출자에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-105">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="c2639-106">소스 코드 파일 경로, 소스 코드 줄 번호 및 호출자의 멤버 이름을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-106">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="c2639-107">이 정보는 추적, 디버깅 및 진단 도구를 만드는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-107">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>

<span data-ttu-id="c2639-108">이 정보를 얻으려면 각각 기본값이 있는 선택적 매개 변수에 적용되는 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-108">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="c2639-109">다음 표에서 목록에 정의 된 호출자 정보 특성은 [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) 네임 스페이스:</span><span class="sxs-lookup"><span data-stu-id="c2639-109">The following table lists the Caller Info attributes that are defined in the [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) namespace:</span></span>

|<span data-ttu-id="c2639-110">특성</span><span class="sxs-lookup"><span data-stu-id="c2639-110">Attribute</span></span>|<span data-ttu-id="c2639-111">설명</span><span class="sxs-lookup"><span data-stu-id="c2639-111">Description</span></span>|<span data-ttu-id="c2639-112">형식</span><span class="sxs-lookup"><span data-stu-id="c2639-112">Type</span></span>|
|---------|-----------|----|
|[<span data-ttu-id="c2639-113">CallerFilePath</span><span class="sxs-lookup"><span data-stu-id="c2639-113">CallerFilePath</span></span>](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|<span data-ttu-id="c2639-114">호출자를 포함한 소스 파일의 전체 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-114">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="c2639-115">컴파일 시간의 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-115">This is the file path at compile time.</span></span>|`String`
|[<span data-ttu-id="c2639-116">CallerLineNumber</span><span class="sxs-lookup"><span data-stu-id="c2639-116">CallerLineNumber</span></span>](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|<span data-ttu-id="c2639-117">메서드가 호출되는 소스 파일의 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-117">Line number in the source file at which the method is called.</span></span>|`Integer`|
|[<span data-ttu-id="c2639-118">CallerMemberName</span><span class="sxs-lookup"><span data-stu-id="c2639-118">CallerMemberName</span></span>](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|<span data-ttu-id="c2639-119">호출자의 메서드 또는 속성 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-119">Method or property name of the caller.</span></span> <span data-ttu-id="c2639-120">이 항목의 뒷부분에 나오는 멤버 이름 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c2639-120">See the Member Names section later in this topic.</span></span>|`String`|

## <a name="example"></a><span data-ttu-id="c2639-121">예제</span><span class="sxs-lookup"><span data-stu-id="c2639-121">Example</span></span>

<span data-ttu-id="c2639-122">다음 예에서는 호출자를 추적 하려면 이러한 특성을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-122">The following example shows how you might use these attributes to trace a caller.</span></span>

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices

type Tracer() =
    member __.DoTrace(msg: string,
                      [<CallerMemberName>] ?memberName: string,
                      [<CallerFilePath>] ?path: string
                      [<CallerLineNumber>] ?line: int) =
        Trace.WriteLine(sprintf "Message: %s" message)
        match (memberName, path, line) with
        | Some m, Some p, Some l ->
            Trace.WriteLine(sprintf "Member name: %s" m)
            Trace.WriteLine(sprintf "Source file path: %s" p)
            Trace.WriteLine(sprintf "Source line number: %d" l)
        | _,_,_ -> ()
```

## <a name="remarks"></a><span data-ttu-id="c2639-123">설명</span><span class="sxs-lookup"><span data-stu-id="c2639-123">Remarks</span></span>

<span data-ttu-id="c2639-124">호출자 정보 특성은 선택적 매개 변수에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-124">Caller Info attributes can only be applied to optional parameters.</span></span> <span data-ttu-id="c2639-125">각 선택적 매개 변수에 대해 명시적 값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-125">You must supply an explicit value for each optional parameter.</span></span> <span data-ttu-id="c2639-126">호출자 정보 특성을 사용 하면 컴파일러가 각 선택적 매개 변수에 호출자 정보 특성으로 데코레이팅된에 대 한 적절 한 값을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-126">The Caller Info attributes cause the compiler to write the proper value for each optional parameter decorated with a Caller Info attribute.</span></span>

<span data-ttu-id="c2639-127">호출자 정보 값은 컴파일 시간에 리터럴로 중간 언어(IL) 내로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-127">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="c2639-128">결과 달리는 [StackTrace](/dotnet/api/system.diagnostics.stacktrace) 예외를 결과 대 한 속성은 난독 화의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-128">Unlike the results of the [StackTrace](/dotnet/api/system.diagnostics.stacktrace) property for exceptions, the results aren't affected by obfuscation.</span></span>

<span data-ttu-id="c2639-129">선택적 인수를 명시적으로 제공하여 호출자 정보를 제어하거나 호출자 정보를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-129">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

## <a name="member-names"></a><span data-ttu-id="c2639-130">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="c2639-130">Member names</span></span>

<span data-ttu-id="c2639-131">사용할 수는 [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) 특성 멤버 이름을 지정 하지 않으려면는 `String` 호출된 된 메서드에 대 한 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-131">You can use the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="c2639-132">이 기술을 사용 하 여 이름 바꾸기 리팩터링 변경 되지 않는 문제를 방지 하는 `String` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-132">By using this technique, you avoid the problem that Rename Refactoring doesn't change the `String` values.</span></span> <span data-ttu-id="c2639-133">이 이점은 다음 작업에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-133">This benefit is especially useful for the following tasks:</span></span>

* <span data-ttu-id="c2639-134">추적 및 진단 루틴 사용.</span><span class="sxs-lookup"><span data-stu-id="c2639-134">Using tracing and diagnostic routines.</span></span>
* <span data-ttu-id="c2639-135">구현 된 [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) 데이터 바인딩할 때 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-135">Implementing the [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interface when binding data.</span></span> <span data-ttu-id="c2639-136">이 인터페이스에서는 컨트롤에서 업데이트된 정보를 표시할 수 있도록 바운드 컨트롤의 속성이 변경되었음을 알리는 개체의 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-136">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="c2639-137">없이 [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) 특성을 속성 이름을 리터럴로 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-137">Without the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="c2639-138">다음 차트에는 멤버 CallerMemberName 특성을 사용 하는 경우 반환 되는 이름이 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-138">The following chart shows the member names that are returned when you use the CallerMemberName attribute.</span></span>

|<span data-ttu-id="c2639-139">호출 발생 범위</span><span class="sxs-lookup"><span data-stu-id="c2639-139">Calls occurs within</span></span>|<span data-ttu-id="c2639-140">멤버 이름 결과</span><span class="sxs-lookup"><span data-stu-id="c2639-140">Member name result</span></span>|
|-------------------|------------------|
|<span data-ttu-id="c2639-141">메서드, 속성 또는 이벤트</span><span class="sxs-lookup"><span data-stu-id="c2639-141">Method, property, or event</span></span>|<span data-ttu-id="c2639-142">호출에서 시작한 메서드, 속성 또는 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-142">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="c2639-143">생성자</span><span class="sxs-lookup"><span data-stu-id="c2639-143">Constructor</span></span>|<span data-ttu-id="c2639-144">".ctor" 문자열</span><span class="sxs-lookup"><span data-stu-id="c2639-144">The string ".ctor"</span></span>|
|<span data-ttu-id="c2639-145">정적 생성자</span><span class="sxs-lookup"><span data-stu-id="c2639-145">Static constructor</span></span>|<span data-ttu-id="c2639-146">".cctor" 문자열</span><span class="sxs-lookup"><span data-stu-id="c2639-146">The string ".cctor"</span></span>|
|<span data-ttu-id="c2639-147">소멸자</span><span class="sxs-lookup"><span data-stu-id="c2639-147">Destructor</span></span>|<span data-ttu-id="c2639-148">"Finalize" 문자열</span><span class="sxs-lookup"><span data-stu-id="c2639-148">The string "Finalize"</span></span>|
|<span data-ttu-id="c2639-149">사용자 정의 연산자 또는 변환</span><span class="sxs-lookup"><span data-stu-id="c2639-149">User-defined operators or conversions</span></span>|<span data-ttu-id="c2639-150">멤버에 대해 생성되는 이름입니다(예: "op_Addition").</span><span class="sxs-lookup"><span data-stu-id="c2639-150">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="c2639-151">특성 생성자</span><span class="sxs-lookup"><span data-stu-id="c2639-151">Attribute constructor</span></span>|<span data-ttu-id="c2639-152">특성이 적용되는 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-152">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="c2639-153">특성이 멤버 내에 있는 어떤 요소인 경우(예: 매개 변수, 반환 값 또는 제네릭 형식 매개 변수) 이 결과는 그 요소와 관련된 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-153">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="c2639-154">포함하는 멤버가 없음(예: 어셈블리 수준 또는 형식에 적용되는 특성)</span><span class="sxs-lookup"><span data-stu-id="c2639-154">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="c2639-155">선택적 매개 변수의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="c2639-155">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="c2639-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2639-156">See also</span></span>
 [<span data-ttu-id="c2639-157">특성</span><span class="sxs-lookup"><span data-stu-id="c2639-157">Attributes</span></span>](attributes.md)  
 [<span data-ttu-id="c2639-158">명명 된 인수</span><span class="sxs-lookup"><span data-stu-id="c2639-158">Named arguments</span></span>](parameters-and-arguments.md#named-arguments)  
 [<span data-ttu-id="c2639-159">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="c2639-159">Optional parameters</span></span>](parameters-and-arguments.md#optional-parameters)  
