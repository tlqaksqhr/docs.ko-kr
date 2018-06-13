---
title: RangeEnumeration 활동
ms.date: 03/30/2017
ms.assetid: ca5b78f4-94fa-4aa7-830d-26039ac422c8
ms.openlocfilehash: 9aa04c80f20e2d410fb49e2d07d836c8c5ab1b4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516580"
---
# <a name="rangeenumeration-activity"></a><span data-ttu-id="89df6-102">RangeEnumeration 활동</span><span class="sxs-lookup"><span data-stu-id="89df6-102">RangeEnumeration Activity</span></span>
<span data-ttu-id="89df6-103">이 샘플에서는 숫자 컬렉션을 반복하는 사용자 지정 활동을 만드는 방법을 보여 줍니다. 다음 표에는 이 샘플에 포함된 주요 파일에 대한 세부 사항이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89df6-103">This sample demonstrates how to create a custom activity that iterates over a collection of numbers.The following table details the main files included in the sample.</span></span>  
  
|<span data-ttu-id="89df6-104">파일 이름</span><span class="sxs-lookup"><span data-stu-id="89df6-104">File name</span></span>|<span data-ttu-id="89df6-105">설명</span><span class="sxs-lookup"><span data-stu-id="89df6-105">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="89df6-106">RangeEnumeration.cs</span><span class="sxs-lookup"><span data-stu-id="89df6-106">RangeEnumeration.cs</span></span>|<span data-ttu-id="89df6-107">`RangeEnumeration` 클래스를 재정의하고 일련의 숫자를 반복하는 <xref:System.Activities.NativeActivity>이라는 사용자 지정 활동을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="89df6-107">Defines a custom activity named `RangeEnumeration` that overrides the <xref:System.Activities.NativeActivity> class and loops through a series of numbers.</span></span>|  
|<span data-ttu-id="89df6-108">RangeEnumerationSample.cs</span><span class="sxs-lookup"><span data-stu-id="89df6-108">RangeEnumerationSample.cs</span></span>|<span data-ttu-id="89df6-109">`RangeEnumeration` 활동을 사용하여 숫자 컬렉션을 반복하는 클라이언트 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="89df6-109">A client application that uses the `RangeEnumeration` activity to iterate over a collection of numbers.</span></span>|  
  
 <span data-ttu-id="89df6-110">다음 표에는 `RangeEnumeration` 활동의 속성에 대한 자세한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89df6-110">The following table details the properties of the `RangeEnumeration` activity.</span></span>  
  
|<span data-ttu-id="89df6-111">속성</span><span class="sxs-lookup"><span data-stu-id="89df6-111">Property</span></span>|<span data-ttu-id="89df6-112">설명</span><span class="sxs-lookup"><span data-stu-id="89df6-112">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="89df6-113">시작</span><span class="sxs-lookup"><span data-stu-id="89df6-113">Start</span></span>|<span data-ttu-id="89df6-114">루프를 시작할 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="89df6-114">The integer to start the loop from.</span></span>|  
|<span data-ttu-id="89df6-115">중지</span><span class="sxs-lookup"><span data-stu-id="89df6-115">Stop</span></span>|<span data-ttu-id="89df6-116">루프를 중지할 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="89df6-116">The integer to stop the loop at.</span></span>|  
|<span data-ttu-id="89df6-117">단계</span><span class="sxs-lookup"><span data-stu-id="89df6-117">Step</span></span>|<span data-ttu-id="89df6-118">반복 과정에서 매번 얼마나 진행할지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="89df6-118">Specifies how much to iterate each time.</span></span>|  
|<span data-ttu-id="89df6-119">Body</span><span class="sxs-lookup"><span data-stu-id="89df6-119">Body</span></span>|<span data-ttu-id="89df6-120">각 반복 과정에서 실행할 코드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="89df6-120">Specifies the code to execute during each iteration.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="89df6-121">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="89df6-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="89df6-122">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 RangeEnumeration.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="89df6-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the RangeEnumeration.sln solution file.</span></span>  
  
2.  <span data-ttu-id="89df6-123">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="89df6-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="89df6-124">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="89df6-124">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="89df6-125">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89df6-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="89df6-126">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="89df6-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="89df6-127">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="89df6-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="89df6-128">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89df6-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\RangeEnumeration`