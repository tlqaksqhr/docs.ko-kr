---
title: While 활동의 열거 중단
ms.date: 03/30/2017
ms.assetid: ddff715d-d623-4b54-b841-60bacbc3ca21
ms.openlocfilehash: 37c64c2b8dc03d58f9c2802edef644fe4888e87d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514715"
---
# <a name="emulating-breaking-in-a-while-activity"></a><span data-ttu-id="68041-102">While 활동의 열거 중단</span><span class="sxs-lookup"><span data-stu-id="68041-102">Emulating breaking in a While activity</span></span>
<span data-ttu-id="68041-103">이 샘플에서는 <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.While> 및 <xref:System.Activities.Statements.ParallelForEach%601> 활동의 루프 메커니즘을 중단하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="68041-103">This sample demonstrates how to break the looping mechanism of the following activities: <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.While>, and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span>  
  
 <span data-ttu-id="68041-104">Windows WF (Workflow Foundation) 이러한 루프의 실행을 중단 하는 활동이 전혀 포함 하지 않기 때문에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="68041-104">This is useful because Windows Workflow Foundation (WF) does not include any activity to break the execution of these loops.</span></span>  
  
## <a name="scenario"></a><span data-ttu-id="68041-105">시나리오</span><span class="sxs-lookup"><span data-stu-id="68041-105">Scenario</span></span>  
 <span data-ttu-id="68041-106">이 샘플에서는 `Vendor` 클래스의 인스턴스인 공급업체 목록 중 신뢰할 수 있는 첫째 공급업체를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="68041-106">The sample finds the first reliable vendor from a list of vendors (instances of the `Vendor` class).</span></span> <span data-ttu-id="68041-107">각 공급업체에는 `ID`와 `Name` 및 공급업체의 신뢰도를 나타내는 숫자 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68041-107">Each vendor has an `ID`, a `Name` and a numeric reliability value that determines how dependable the vendor is.</span></span> <span data-ttu-id="68041-108">이 샘플에서는 공급업체 목록과 최소 신뢰도 값을 나타내는 입력 매개 변수 두 개를 받고 목록 중 지정된 조건에 일치하는 첫째 공급업체를 반환하는 `FindReliableVendor`라는 사용자 지정 활동을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="68041-108">The sample creates a custom activity called `FindReliableVendor` that receives two input parameters (a list of vendors and a minimum reliability value) and returns the first vendor of the list that matches the supplied criteria.</span></span>  
  
## <a name="breaking-a-loop"></a><span data-ttu-id="68041-109">루프 중단</span><span class="sxs-lookup"><span data-stu-id="68041-109">Breaking a Loop</span></span>  
 <span data-ttu-id="68041-110">Windows WF (Workflow Foundation)는 루프를 중단 하는 활동을 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68041-110">Windows Workflow Foundation (WF) does not include an activity to break a loop.</span></span> <span data-ttu-id="68041-111">이 코드 샘플에서는 <xref:System.Activities.Statements.If> 활동과 여러 가지 변수를 사용하여 루프를 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="68041-111">The code sample accomplishes breaking a loop by using an <xref:System.Activities.Statements.If> activity and several variables.</span></span> <span data-ttu-id="68041-112">이 샘플에서 <xref:System.Activities.Statements.While> 변수에 `reliableVendor`이 아닌 다른 값이 할당되면 `null` 활동이 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="68041-112">In the sample, the <xref:System.Activities.Statements.While> activity is broken once the `reliableVendor` variable is assigned a value other than `null`.</span></span>  
  
 <span data-ttu-id="68041-113">다음 코드 예제에서는 이 샘플을 통해 while 루프가 어떻게 중단되는지 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="68041-113">The following code example demonstrates how the sample breaks a while loop.</span></span>  
  
```csharp  
// Iterates while the "i" variable is lower than the size of the list   
// and any reliable Vendor is found.        
new While(env => i.Get(env) < this.Vendors.Get(env).Count && reliableVendor.Get(env) == null)  
{  
    DisplayName = "Main loop. Breaks when a reliable vendor is found",  
    Body = new Sequence  
    {                              
        Activities =  
        {  
            // This is the if used for setting the value of the break value…  
            new If  
            {  
                DisplayName = "Check for a reliable vendor",  
  
                //  If a vendor satisfies the reliability level…  
                Condition = new InArgument<bool>(env =>   
                           this.Vendors.Get(env)[i.Get(env)].Reliability >   
                           this.MinimumReliability.Get(env)),  
  
                // then assign that vendor to the reliable vendor variable and   
                // the while condition becomes false (exit the loop).  
                Then = new Assign<Vendor>  
                {  
                    To = reliableVendor,  
                    Value = new InArgument<Vendor>(env =>   
                                  this.Vendors.Get(env)[i.Get(env)])  
                }  
            },  
  
            // Increment the iteration variable.   
            new Assign<int>  
            {  
                DisplayName = "Increment iteration variable",  
                To = i,  
                Value = new InArgument<int>(env => i.Get(env) + 1)  
            }   
        }  
    }  
}  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="68041-114">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="68041-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="68041-115">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 EmulatingBreakInWhile.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="68041-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the EmulatingBreakInWhile.sln solution file.</span></span>  
  
2.  <span data-ttu-id="68041-116">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="68041-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="68041-117">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="68041-117">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="68041-118">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68041-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="68041-119">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="68041-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="68041-120">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="68041-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="68041-121">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68041-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\EmulatingBreakInWhile`