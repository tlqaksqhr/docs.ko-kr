---
title: "활동 유효성 검사 호출"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22bef766-c505-4fd4-ac0f-7b363b238969
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f089abdf4c534a5016185e5a6f52067f46693604
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="invoking-activity-validation"></a><span data-ttu-id="0398d-102">활동 유효성 검사 호출</span><span class="sxs-lookup"><span data-stu-id="0398d-102">Invoking Activity Validation</span></span>
<span data-ttu-id="0398d-103">활동 유효성 검사를 사용하면 활동을 실행하기 이전에 활동 구성 오류를 식별하여 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-103">Activity validation provides a method to identify and report errors in any activity’s configuration prior to its execution.</span></span> <span data-ttu-id="0398d-104">Workflow Designer에서 워크플로를 수정하면 유효성 검사가 수행되어 Workflow Designer에 유효성 검사 오류 또는 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-104">Validation occurs when a workflow is modified in the workflow designer and any validation errors or warnings are displayed in the workflow designer.</span></span> <span data-ttu-id="0398d-105">워크플로를 호출하면 런타임에도 유효성 검사가 수행되며 유효성 검사 오류가 발생할 경우 기본 유효성 검사 논리에 따라 <xref:System.Activities.InvalidWorkflowException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-105">Validation also occurs at run time when a workflow is invoked and if any validation errors occur, an <xref:System.Activities.InvalidWorkflowException> is thrown by the default validation logic.</span></span> [!INCLUDE[wf](../../../includes/wf-md.md)]<span data-ttu-id="0398d-106">는 활동의 유효성을 명시적으로 검사하기 위해 워크플로 응용 프로그램 및 도구 개발자가 사용할 수 있는 <xref:System.Activities.Validation.ActivityValidationServices> 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-106"> provides the <xref:System.Activities.Validation.ActivityValidationServices> class that can be used by workflow application and tooling developers to explicitly validate an activity.</span></span> <span data-ttu-id="0398d-107">이 항목에서는 <xref:System.Activities.Validation.ActivityValidationServices>를 사용하여 활동 유효성 검사를 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-107">This topic describes how to use <xref:System.Activities.Validation.ActivityValidationServices> to perform activity validation.</span></span>  
  
## <a name="using-activityvalidationservices"></a><span data-ttu-id="0398d-108">ActivityValidationServices 사용</span><span class="sxs-lookup"><span data-stu-id="0398d-108">Using ActivityValidationServices</span></span>  
 <span data-ttu-id="0398d-109"><xref:System.Activities.Validation.ActivityValidationServices>에는 활동 유효성 검사 논리를 호출하는 데 사용되는 두 가지 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> 오버로드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-109"><xref:System.Activities.Validation.ActivityValidationServices> has two <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> overloads that are used to invoke an activity’s validation logic.</span></span> <span data-ttu-id="0398d-110">첫 번째 오버로드에서는 루트 활동의 유효성 검사하고 유효성 검사 및 경고 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-110">The first overload takes the root activity to be validated and returns a collection of validation errors and warnings.</span></span> <span data-ttu-id="0398d-111">다음 예제에서는 두 필수 인수를 가진 사용자 지정 `Add` 활동을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-111">In the following example, a custom `Add` activity is used that has two required arguments.</span></span>  
  
```csharp  
public sealed class Add : CodeActivity<int>  
{  
    [RequiredArgument]  
    public InArgument<int> Operand1 { get; set; }  
  
    [RequiredArgument]  
    public InArgument<int> Operand2 { get; set; }  
  
    protected override int Execute(CodeActivityContext context)  
    {  
        return Operand1.Get(context) + Operand2.Get(context);  
    }  
}  
```  
  
 <span data-ttu-id="0398d-112">다음 예제에 표시된 것처럼 `Add` 활동은 <xref:System.Activities.Statements.Sequence> 내에서 사용되지만 두 필수 인수가 바인딩되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-112">The `Add` activity is used inside a <xref:System.Activities.Statements.Sequence>, but its two required arguments are not bound, as shown in the following example.</span></span>  
  
```csharp  
Variable<int> Operand1 = new Variable<int>{ Default = 10 };  
Variable<int> Operand2 = new Variable<int>{ Default = 15 };  
Variable<int> Result = new Variable<int>();  
  
Activity wf = new Sequence  
{  
    Variables = { Operand1, Operand2, Result },  
    Activities =   
    {  
        new Add(),  
        new WriteLine  
        {  
            Text = new InArgument<string>(env => "The result is " + Result.Get(env))  
        }  
    }  
};  
```  
  
 <span data-ttu-id="0398d-113"><xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>를 호출하여 이 워크플로의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-113">This workflow can be validated by calling <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span></span> <span data-ttu-id="0398d-114">다음 예에 표시된 것처럼 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>는 활동과 해당 자식에 포함된 유효성 검사 오류 또는 경고 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-114"><xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> returns a collection of any validation errors or warnings contained by the activity and any children, as shown in the following example.</span></span>  
  
```csharp  
ValidationResults results = ActivityValidationServices.Validate(wf);  
  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error: {0}", error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning: {0}", warning.Message);  
    }  
}  
```  
  
 <span data-ttu-id="0398d-115">이 샘플 워크플로에서 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>를 호출하면 두 유효성 검사 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-115">When <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> is called on this sample workflow, two validation errors are returned.</span></span>  
  
 <span data-ttu-id="0398d-116">**오류: 필수 작업 인수 'Operand2'에 대 한 값을 제공 하지 않았습니다.**</span><span class="sxs-lookup"><span data-stu-id="0398d-116">**Error: Value for a required activity argument 'Operand2' was not supplied.**</span></span>  
<span data-ttu-id="0398d-117">**오류: 필수 작업 인수 'Operand1'에 대 한 값을 제공 하지 않았습니다.**</span><span class="sxs-lookup"><span data-stu-id="0398d-117">**Error: Value for a required activity argument 'Operand1' was not supplied.**</span></span>  <span data-ttu-id="0398d-118">이 워크플로를 호출하면 다음 예제처럼 <xref:System.Activities.InvalidWorkflowException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-118">If this workflow was invoked, an <xref:System.Activities.InvalidWorkflowException> would be thrown, as shown in the following example.</span></span>  
  
```csharp  
try  
{  
    WorkflowInvoker.Invoke(wf);  
}  
catch (Exception ex)  
{  
    Console.WriteLine(ex);  
}  
```  
  
 <span data-ttu-id="0398d-119">**System.Activities.InvalidWorkflowException:**</span><span class="sxs-lookup"><span data-stu-id="0398d-119">**System.Activities.InvalidWorkflowException:**</span></span>  
<span data-ttu-id="0398d-120">**워크플로 트리를 처리 하는 동안 다음 오류가 발생 했습니다.** </span><span class="sxs-lookup"><span data-stu-id="0398d-120">**The following errors were encountered while processing the workflow tree:** </span></span>  
<span data-ttu-id="0398d-121">**'Add': 값이 필수 작업 인수 'Operand2' 제공 되지 않았습니다.** </span><span class="sxs-lookup"><span data-stu-id="0398d-121">**'Add': Value for a required activity argument 'Operand2' was not supplied.** </span></span>  
<span data-ttu-id="0398d-122">**'Add': 값이 필수 작업 인수 'Operand1' 제공 되지 않았습니다.**</span><span class="sxs-lookup"><span data-stu-id="0398d-122">**'Add': Value for a required activity argument 'Operand1' was not supplied.**</span></span>  <span data-ttu-id="0398d-123">이 예제 워크플로가 유효하려면 `Add` 활동의 두 필수 인수가 바인딩되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-123">For this example workflow to be valid, the two required arguments of the `Add` activity must be bound.</span></span> <span data-ttu-id="0398d-124">다음 예제에서는 두 필수 인수가 워크플로 변수에 결과 값과 함께 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-124">In the following example, the two required arguments are bound to workflow variables along with the result value.</span></span> <span data-ttu-id="0398d-125">이 예제에서 <xref:System.Activities.Activity%601.Result%2A> 인수는 두 필수 인수와 함께 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-125">In this example the <xref:System.Activities.Activity%601.Result%2A> argument is bound along with the two required arguments.</span></span> <span data-ttu-id="0398d-126"><xref:System.Activities.Activity%601.Result%2A> 인수는 바인딩될 필요가 없으므로 바인딩되지 않더라도 유효성 검사 오류가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-126">The <xref:System.Activities.Activity%601.Result%2A> argument is not required to be bound and does not cause a validation error if it is not.</span></span> <span data-ttu-id="0398d-127"><xref:System.Activities.Activity%601.Result%2A> 인수의 값이 워크플로의 다른 위치에서 사용될 경우 워크플로 작성자가 이 인수를 바인딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-127">It is the responsibility of the workflow author to bind <xref:System.Activities.Activity%601.Result%2A> if its value is used elsewhere in the workflow.</span></span>  
  
```csharp  
new Add  
{  
    Operand1 = Operand1,  
    Operand2 = Operand2,  
    Result = Result  
}  
```  
  
### <a name="validating-required-arguments-on-the-root-activity"></a><span data-ttu-id="0398d-128">루트 활동의 필수 인수 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="0398d-128">Validating Required Arguments on the Root Activity</span></span>  
 <span data-ttu-id="0398d-129">워크플로의 루트 활동에 인수가 있는 경우 워크플로를 호출하여 매개 변수가 워크플로에 전달될 때까지는 해당 인수가 바인딩되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-129">If the root activity of a workflow has arguments, these are not bound until the workflow is invoked and parameters are passed to the workflow.</span></span> <span data-ttu-id="0398d-130">따라서 다음 예제처럼 필수 인수를 전달하지 않고 워크플로를 호출하면 다음 워크플로가 유효성을 통과하지만 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-130">The following workflow passes validation, but an exception is thrown if the workflow is invoked without passing in the required arguments, as shown in the following example.</span></span>  
  
```csharp  
Activity wf = new Add();  
  
ValidationResults results = ActivityValidationServices.Validate(wf);  
// results has no errors or warnings, but when the workflow  
// is invoked, an InvalidWorkflowException is thrown.  
try  
{  
    WorkflowInvoker.Invoke(wf);  
}  
catch (Exception ex)  
{  
    Console.WriteLine(ex);  
}  
```  
  
 <span data-ttu-id="0398d-131">**System.ArgumentException: 루트 활동의 인수 설정이 올바르지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="0398d-131">**System.ArgumentException: The root activity's argument settings are incorrect.**</span></span>  
<span data-ttu-id="0398d-132">**워크플로 정의 수정 하거나 이러한 오류를 해결 하려면 입력된 값을 제공 합니다.** </span><span class="sxs-lookup"><span data-stu-id="0398d-132">**Either fix the workflow definition or supply input values to fix these errors:** </span></span>  
<span data-ttu-id="0398d-133">**'Add': 값이 필수 작업 인수 'Operand2' 제공 되지 않았습니다.** </span><span class="sxs-lookup"><span data-stu-id="0398d-133">**'Add': Value for a required activity argument 'Operand2' was not supplied.** </span></span>  
<span data-ttu-id="0398d-134">**'Add': 값이 필수 작업 인수 'Operand1' 제공 되지 않았습니다.**</span><span class="sxs-lookup"><span data-stu-id="0398d-134">**'Add': Value for a required activity argument 'Operand1' was not supplied.**</span></span>  <span data-ttu-id="0398d-135">다음 예제처럼 올바른 인수가 전달되면 워크플로가 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-135">After the correct arguments are passed, the workflow completes successfully, as shown in the following example.</span></span>  
  
```csharp  
Add wf = new Add();  
  
ValidationResults results = ActivityValidationServices.Validate(wf);  
// results has no errors or warnings, and the workflow completes  
// successfully because the required arguments were passed.  
try  
{  
    Dictionary<string, object> wfparams = new Dictionary<string, object>  
    {  
        { "Operand1", 10 },  
        { "Operand2", 15 }  
    };  
  
    int result = WorkflowInvoker.Invoke(wf, wfparams);  
    Console.WriteLine("Result: {0}", result);  
}  
catch (Exception ex)  
{  
    Console.WriteLine(ex);  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="0398d-136">이 예제에서는 이전 예제처럼 루트 활동을 `Add`로 선언하는 대신 `Activity`로 선언했습니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-136">In this example, the root activity was declared as `Add` instead of `Activity` as in the previous example.</span></span> <span data-ttu-id="0398d-137">이렇게 하면 `WorkflowInvoker.Invoke` 메서드가 `Add` 인수 사전 대신 `out` 활동 결과를 나타내는 단일 정수를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-137">This allows the `WorkflowInvoker.Invoke` method to return a single integer that represents the results of the `Add` activity instead of a dictionary of `out` arguments.</span></span> <span data-ttu-id="0398d-138">변수 `wf`가 `Activity<int>`로 선언되었을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-138">The variable `wf` could also have been declared as `Activity<int>`.</span></span>  
  
 <span data-ttu-id="0398d-139">루트 인수의 유효성을 검사할 때 호스트 응용 프로그램에서는 워크플로를 호출할 때 모든 필수 인수가 전달되는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-139">When validating root arguments, it is the responsibility of the host application to ensure that all required arguments are passed when the workflow is invoked.</span></span>  
  
### <a name="invoking-imperative-code-based-validation"></a><span data-ttu-id="0398d-140">명령 코드 기반 유효성 검사 호출</span><span class="sxs-lookup"><span data-stu-id="0398d-140">Invoking Imperative Code-Based Validation</span></span>  
 <span data-ttu-id="0398d-141">명령형 코드 기반 유효성 검사를 이용하면 활동 자체에서 활동 유효성 검사를 간단히 실행할 수 있으며 <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> 및 <xref:System.Activities.NativeActivity>의 파생 활동에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-141">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and is available for activities that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, and <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="0398d-142">유효성 검사 오류 또는 경고를 판단하는 유효성 검사 코드가 활동에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-142">Validation code that determines any validation errors or warnings is added to the activity.</span></span> <span data-ttu-id="0398d-143">활동에 유효성 검사가 호출되면 이러한 경고 또는 오류가 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> 호출에서 반환된 컬렉션에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-143">When validation is invoked on the activity, these warnings or errors are contained in the collection returned by the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span></span> <span data-ttu-id="0398d-144">다음 예제에서에서 가져온는 [기본 유효성 검사](../../../docs/framework/windows-workflow-foundation/samples/basic-validation.md) 샘플에서는 한 `CreateProduct` 활동을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-144">In the following example, taken from the [Basic Validation](../../../docs/framework/windows-workflow-foundation/samples/basic-validation.md) sample, a `CreateProduct` activity is defined.</span></span> <span data-ttu-id="0398d-145">다음 예에서 `Cost`가 `Price`보다 크면 <xref:System.Activities.CodeActivity.CacheMetadata%2A> 재정의 메타데이터에 유효성 검사 오류가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-145">If the `Cost` is greater than the `Price`, a validation error is added to the metadata in the <xref:System.Activities.CodeActivity.CacheMetadata%2A> override.</span></span>  
  
```csharp  
public sealed class CreateProduct : CodeActivity  
{  
    public double Price { get; set; }  
    public double Cost { get; set; }  
  
    // [RequiredArgument] attribute will generate a validation error   
    // if the Description argument is not set.  
    [RequiredArgument]  
    public InArgument<string> Description { get; set; }  
  
    protected override void CacheMetadata(CodeActivityMetadata metadata)  
    {  
        base.CacheMetadata(metadata);  
        // Determine when the activity has been configured in an invalid way.  
        if (this.Cost > this.Price)  
        {  
            // Add a validation error with a custom message.  
            metadata.AddValidationError("The Cost must be less than or equal to the Price.");  
        }  
    }  
  
    protected override void Execute(CodeActivityContext context)  
    {  
        // Not needed for the sample.  
    }  
}  
```  
  
 <span data-ttu-id="0398d-146">이 예제에서 워크플로는 `CreateProduct` 활동을 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-146">In this example, a workflow is configured using the `CreateProduct` activity.</span></span> <span data-ttu-id="0398d-147">이 워크플로에서 `Cost`는 `Price`보다 크고 필수 `Description` 인수는 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-147">In this workflow, the `Cost` is greater than the `Price`, and the required `Description` argument is not set.</span></span> <span data-ttu-id="0398d-148">유효성 검사가 호출되면 다음 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-148">When validation is invoked, the following errors are returned.</span></span>  
  
```csharp  
Activity wf = new Sequence  
{  
    Activities =   
    {  
        new CreateProduct  
        {  
            Cost = 75.00,  
            Price = 55.00  
            // Cost > Price and required Description argument not set.  
        },  
        new WriteLine  
        {  
            Text = "Product added."  
        }  
    }  
};  
  
ValidationResults results = ActivityValidationServices.Validate(wf);  
  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error: {0}", error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning: {0}", warning.Message);  
    }  
}  
```  
  
 <span data-ttu-id="0398d-149">**오류: 비용은 가격 보다 작거나 이어야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="0398d-149">**Error: The Cost must be less than or equal to the Price.**</span></span>  
<span data-ttu-id="0398d-150">**오류: 필수 작업 인수 'Description'에 대 한 값을 제공 하지 않았습니다.**</span><span class="sxs-lookup"><span data-stu-id="0398d-150">**Error: Value for a required activity argument 'Description' was not supplied.**</span></span>    
> [!NOTE]
>  <span data-ttu-id="0398d-151">사용자 지정 활동 작성자는 활동의 <xref:System.Activities.CodeActivity.CacheMetadata%2A> 재정의에서 유효성 검사 논리를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-151">Custom activity authors can provide validation logic in an activity's <xref:System.Activities.CodeActivity.CacheMetadata%2A> override.</span></span> <span data-ttu-id="0398d-152"><xref:System.Activities.CodeActivity.CacheMetadata%2A>에서 throw되는 모든 예외는 유효성 검사 오류로 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-152">Any exceptions that are thrown from <xref:System.Activities.CodeActivity.CacheMetadata%2A> are not treated as validation errors.</span></span> <span data-ttu-id="0398d-153">이러한 예외는 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>에 대한 호출에서 이스케이프되며 호출자가 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-153">These exceptions will escape from the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> and must be handled by the caller.</span></span>  
  
## <a name="using-validationsettings"></a><span data-ttu-id="0398d-154">ValidationSettings 사용</span><span class="sxs-lookup"><span data-stu-id="0398d-154">Using ValidationSettings</span></span>  
 <span data-ttu-id="0398d-155"><xref:System.Activities.Validation.ActivityValidationServices>에서 유효성 검사를 호출하면 기본적으로 활동 트리의 모든 활동이 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-155">By default, all activities in the activity tree are evaluated when validation is invoked by <xref:System.Activities.Validation.ActivityValidationServices>.</span></span> <span data-ttu-id="0398d-156"><xref:System.Activities.Validation.ValidationSettings> 을 사용하면 세 가지 속성을 구성하여 유효성 검사를 다양한 방법으로 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-156"><xref:System.Activities.Validation.ValidationSettings> allows the validation to be customized in several different ways by configuring its three properties.</span></span> <span data-ttu-id="0398d-157"><xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A>은 유효성 검사기에서 전체 활동 트리를 검사해야 할지 또는 제공된 활동에만 유효성 검사 논리를 적용해야 할지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-157"><xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> specifies whether the validator should walk the entire activity tree or only apply validation logic to the supplied activity.</span></span> <span data-ttu-id="0398d-158">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-158">The default for this value is `false`.</span></span> <span data-ttu-id="0398d-159"><xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>는 형식에서 제약 조건 목록으로 매핑하는 추가 제약 조건을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-159"><xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> specifies additional constraint mapping from a type to a list of constraints.</span></span> <span data-ttu-id="0398d-160">유효성을 검사 중인 활동 트리에 있는 각 활동의 기본 형식에 대해 <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>를 조회합니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-160">For the base type of each activity in the activity tree being validated there is a lookup into <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>.</span></span> <span data-ttu-id="0398d-161">일치하는 제약 조건 목록이 있는 경우 활동에 대한 목록의 모든 제약 조건을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-161">If a matching constraint list is found, all constraints in the list are evaluated for the activity.</span></span> <span data-ttu-id="0398d-162"><xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A>는 유효성 검사기에서 모든 제약 조건을 평가해야 할지 또는 <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>에 지정된 제약 조건만 평가해야 할지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-162"><xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> specifies whether the validator should evaluate all constraints or only those specified in <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>.</span></span> <span data-ttu-id="0398d-163">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-163">The default value is `false`.</span></span> <span data-ttu-id="0398d-164"><xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> 및 <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A>는 워크플로 호스트 작성자가 워크플로에 대한 유효성 검사(예: FxCop와 같은 도구에 대한 정책 제약 조건)를 추가하는 데 유용합니다</span><span class="sxs-lookup"><span data-stu-id="0398d-164"><xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> and <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> are useful for workflow host authors to add additional validation for workflows, such as policy constraints for tools such as FxCop.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="0398d-165">제약 조건, 참조 [선언적 제약 조건을](../../../docs/framework/windows-workflow-foundation/declarative-constraints.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-165"> constraints, see [Declarative Constraints](../../../docs/framework/windows-workflow-foundation/declarative-constraints.md).</span></span>  
  
 <span data-ttu-id="0398d-166"><xref:System.Activities.Validation.ValidationSettings>를 사용하려면 원하는 속성을 구성한 다음 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> 호출 시 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-166">To use <xref:System.Activities.Validation.ValidationSettings>, configure the desired properties, and then pass it in the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span></span> <span data-ttu-id="0398d-167">이 예제에서는 <xref:System.Activities.Statements.Sequence>와 사용자 지정 `Add` 활동으로 구성되는 워크플로의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-167">In this example, a workflow that consists of a <xref:System.Activities.Statements.Sequence> with a custom `Add` activity is validated.</span></span> <span data-ttu-id="0398d-168">`Add` 활동에는 두 가지 필수 인수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-168">The `Add` activity has two required arguments.</span></span>  
  
```csharp  
public sealed class Add : CodeActivity<int>  
{  
    [RequiredArgument]  
    public InArgument<int> Operand1 { get; set; }  
  
    [RequiredArgument]  
    public InArgument<int> Operand2 { get; set; }  
  
    protected override int Execute(CodeActivityContext context)  
    {  
        return Operand1.Get(context) + Operand2.Get(context);  
    }  
}  
```  
  
 <span data-ttu-id="0398d-169">다음 `Add` 활동은 <xref:System.Activities.Statements.Sequence>에서 사용되지만 두 필수 인수는 바인딩되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-169">The following `Add` activity is used in a <xref:System.Activities.Statements.Sequence>, but its two required arguments are not bound.</span></span>  
  
```csharp  
Variable<int> Operand1 = new Variable<int> { Default = 10 };  
Variable<int> Operand2 = new Variable<int> { Default = 15 };  
Variable<int> Result = new Variable<int>();  
  
Activity wf = new Sequence  
{  
    Variables = { Operand1, Operand2, Result },  
    Activities =   
    {  
        new Add(),  
        new WriteLine  
        {  
            Text = new InArgument<string>(env => "The result is " + Result.Get(env))  
        }  
    }  
};  
```  
  
 <span data-ttu-id="0398d-170">다음 예제에서는 <xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A>을 `true`로 설정한 상태에서 유효성 검사를 수행하므로 루트 <xref:System.Activities.Statements.Sequence> 활동만 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-170">For the following example, validation is performed with <xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> set to `true`, so only the root <xref:System.Activities.Statements.Sequence> activity is validated.</span></span>  
  
```csharp  
ValidationSettings settings = new ValidationSettings  
{  
    SingleLevel = true  
};  
  
ValidationResults results = ActivityValidationServices.Validate(wf, settings);  
  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error: {0}", error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning: {0}", warning.Message);  
    }  
}  
```  
  
 <span data-ttu-id="0398d-171">이 코드의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-171">This code displays the following output:</span></span>  
  
 <span data-ttu-id="0398d-172">**경고 또는 오류가 없더라도** 있지만 `Add` 활동에 필수 인수가 바인딩되지 않은, 루트 활동만 평가 되기 때문에 유효성 검사를 통과 합니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-172">**No warnings or errors** Even though the `Add` activity has required arguments that are not bound, validation is successful because only the root activity is evaluated.</span></span> <span data-ttu-id="0398d-173">이러한 유형의 유효성 검사는 활동 트리에서 특정 요소만 유효성을 검사(예: 디자이너의 단일 활동에 대한 속성 변경 유효성 검사)할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-173">This type of validation is useful for validating only specific elements in an activity tree, such as validation of a property change of a single activity in a designer.</span></span> <span data-ttu-id="0398d-174">이 워크플로를 호출하면 워크플로에 구성된 전체 유효성 검사가 수행되고 <xref:System.Activities.InvalidWorkflowException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-174">Note that if this workflow is invoked, the full validation configured in the workflow is evaluated and an <xref:System.Activities.InvalidWorkflowException> would be thrown.</span></span> <span data-ttu-id="0398d-175"><xref:System.Activities.Validation.ActivityValidationServices> 및 <xref:System.Activities.Validation.ValidationSettings>는 호스트에서 명시적으로 호출되는 유효성 검사만 구성하고 워크플로를 호출할 때 발생하는 유효성 검사는 구성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0398d-175"><xref:System.Activities.Validation.ActivityValidationServices> and <xref:System.Activities.Validation.ValidationSettings> configure only validation explicitly invoked by the host, and not the validation that occurs when a workflow is invoked.</span></span>
