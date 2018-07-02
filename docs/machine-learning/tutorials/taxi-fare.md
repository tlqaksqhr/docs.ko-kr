---
title: ML.NET을 사용하여 뉴욕 택시 요금 예측(회귀)
description: 회귀 시나리오에서 ML.NET을 사용하는 방법을 알아봅니다.
author: aditidugar
ms.author: johalex
ms.date: 06/05/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 048ed1d38408c1ba4901c554cae33d5552c9e303
ms.sourcegitcommit: 5b0802832fb9ad684d34e69b8644a16a5b7c4810
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2018
ms.locfileid: "34860705"
---
# <a name="tutorial-use-mlnet-to-predict-new-york-taxi-fares-regression"></a><span data-ttu-id="52154-103">자습서: ML.NET을 사용하여 뉴욕 택시 요금 예측(회귀)</span><span class="sxs-lookup"><span data-stu-id="52154-103">Tutorial: Use ML.NET to predict New York taxi fares (regression)</span></span>

> [!NOTE]
> <span data-ttu-id="52154-104">이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52154-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="52154-105">자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52154-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="52154-106">이 자습서에서는 ML.NET을 사용하여 뉴욕시 택시 요금을 예측하기 위한 [회귀 모델](../resources/glossary.md#regression)을 빌드하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-106">This tutorial illustrates how to use ML.NET to build a [regression model](../resources/glossary.md#regression) for predicting New York City taxi fares.</span></span>

<span data-ttu-id="52154-107">이 자습서에서는 다음 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="52154-108">문제 이해</span><span class="sxs-lookup"><span data-stu-id="52154-108">Understand the problem</span></span>
> * <span data-ttu-id="52154-109">적절한 기계 학습 작업 선택</span><span class="sxs-lookup"><span data-stu-id="52154-109">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="52154-110">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="52154-110">Prepare and understand your data</span></span>
> * <span data-ttu-id="52154-111">학습 파이프라인 만들기</span><span class="sxs-lookup"><span data-stu-id="52154-111">Create a learning pipeline</span></span>
> * <span data-ttu-id="52154-112">데이터 로드 및 변환</span><span class="sxs-lookup"><span data-stu-id="52154-112">Load and transform your data</span></span>
> * <span data-ttu-id="52154-113">학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="52154-113">Choose a learning algorithm</span></span>
> * <span data-ttu-id="52154-114">모델 학습</span><span class="sxs-lookup"><span data-stu-id="52154-114">Train the model</span></span>
> * <span data-ttu-id="52154-115">모델 평가</span><span class="sxs-lookup"><span data-stu-id="52154-115">Evaluate the model</span></span>
> * <span data-ttu-id="52154-116">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="52154-116">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="52154-117">전제 조건</span><span class="sxs-lookup"><span data-stu-id="52154-117">Prerequisites</span></span>

* <span data-ttu-id="52154-118">“.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 15.6 이상](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).</span><span class="sxs-lookup"><span data-stu-id="52154-118">[Visual Studio 2017 15.6 or later](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="52154-119">문제 이해</span><span class="sxs-lookup"><span data-stu-id="52154-119">Understand the problem</span></span>

<span data-ttu-id="52154-120">이 문제는 **뉴욕시의 택시 요금을 예측**을 중심으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="52154-120">This problem is centered around **predicting the fare of a taxi trip in New York City**.</span></span> <span data-ttu-id="52154-121">처음에는 요금이 단순히 주행 거리에 따라 결정되는 것처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52154-121">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="52154-122">그러나 뉴욕 택시 업체는 추가 승객 또는 현금 대신 신용 카드 결제 등의 다른 요소를 고려하여 다양한 금액을 청구합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-122">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="52154-123">적절한 기계 학습 작업 선택</span><span class="sxs-lookup"><span data-stu-id="52154-123">Select the appropriate machine learning task</span></span>

<span data-ttu-id="52154-124">택시 요금을 예측하려면 먼저 적절한 기계 학습 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-124">To predict the taxi fare, you first select the appropriate machine learning task.</span></span> <span data-ttu-id="52154-125">데이터 집합의 다른 요소를 기반으로 실제 값(가격을 나타내는 double)을 예측하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-125">You are looking to predict a real value (a double that represents price) based on the other factors in the dataset.</span></span> <span data-ttu-id="52154-126">[**회귀**](../resources/glossary.md#regression) 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-126">You choose a [**regression**](../resources/glossary.md#regression) task.</span></span>

<span data-ttu-id="52154-127">모델 학습 프로세스는 최종 요금 가격을 예측할 때 가장 영향이 큰 데이터 집합의 요소를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-127">The process of training the model identifies which factors in the dataset are most influential when predicting the final fare price.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="52154-128">콘솔 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="52154-128">Create a console application</span></span>

1. <span data-ttu-id="52154-129">Visual Studio 2017을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="52154-129">Open Visual Studio 2017.</span></span> <span data-ttu-id="52154-130">메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-130">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="52154-131">**새 프로젝트** 대화 상자에서 **Visual C#** 노드와 **.NET Core** 노드를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-131">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="52154-132">그런 다음 **콘솔 앱(.NET Core)** 프로젝트 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-132">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="52154-133">**이름** 텍스트 상자에 “TaxiFarePrediction”을 입력하고 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-133">In the **Name** text box, type "TaxiFarePrediction" and then select the **OK** button.</span></span>

2. <span data-ttu-id="52154-134">프로젝트에서 *Data* 디렉터리를 만들어 데이터 집합 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-134">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="52154-135">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 폴더**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-135">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="52154-136">“Data”를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="52154-136">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="52154-137">**Microsoft.ML NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-137">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="52154-138">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-138">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="52154-139">“nuget.org”를 패키지 소스로 선택하고, [찾아보기] 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-139">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="52154-140">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-140">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-and-understand-your-data"></a><span data-ttu-id="52154-141">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="52154-141">Prepare and understand your data</span></span>

1. <span data-ttu-id="52154-142">[taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) 및 [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) 데이터 집합을 다운로드하여 이전에 만든 *Data* 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-142">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="52154-143">Taxi Trip 데이터 집합은 기계 학습 모델을 학습시키며 모델의 정확도를 평가하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52154-143">The Taxi Trip data set trains the machine learning model and can be used to evaluate how accurate your model is.</span></span> <span data-ttu-id="52154-144">이러한 데이터 집합은 원래 [NYC TLC Taxi Trip 데이터 집합](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="52154-144">These data sets are originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

2. <span data-ttu-id="52154-145">솔루션 탐색기에서 각 \*.csv 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-145">In Solution Explorer, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="52154-146">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **항상**으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-146">Under **Advanced**, change the value of **Copy to Output Directory** to **Always**.</span></span>

3. <span data-ttu-id="52154-147">코드 편집기에서 **taxi-fare-train.csv** 데이터 집합을 열고 첫 번째 행에서 열 머리글을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-147">Open the **taxi-fare-train.csv** data set in the code editor and look at column headers in the first row.</span></span> <span data-ttu-id="52154-148">각 열을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="52154-148">Take a look at each of the columns.</span></span> <span data-ttu-id="52154-149">데이터를 이해하고 **기능** 및 **레이블**로 사용할 열을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-149">Understand the data and decide which columns are **features** and which is the **label**.</span></span>

<span data-ttu-id="52154-150">**레이블**은 예측하려는 열의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="52154-150">The **label** is the identifier of the column you are trying to predict.</span></span> <span data-ttu-id="52154-151">식별된 **기능**은 레이블을 예측하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="52154-151">The identified **features** are used to predict the label.</span></span>

* <span data-ttu-id="52154-152">**vendor_id:** 택시 공급업체의 ID가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="52154-152">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="52154-153">**rate_code:** 택시 이동의 요금 유형이 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="52154-153">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="52154-154">**passenger_count:** 이동하는 승객 수가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="52154-154">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="52154-155">**trip_time_in_secs**: 이동에 걸린 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="52154-155">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="52154-156">이동이 완료된 후까지 걸리는 시간은 모릅니다.</span><span class="sxs-lookup"><span data-stu-id="52154-156">You won't know how long the trip takes until after it is completed.</span></span> <span data-ttu-id="52154-157">모델에서 이 열을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-157">You exclude this column from the model.</span></span>
* <span data-ttu-id="52154-158">**trip_distance:** 이동 거리가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="52154-158">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="52154-159">**payment_type:** 결제 방법(현금 또는 신용 카드)이 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="52154-159">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="52154-160">**fare_amount:** 지급한 총 택시 요금이 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="52154-160">**fare_amount:** The total taxi fare paid is the label.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="52154-161">클래스 만들기 및 경로 정의</span><span class="sxs-lookup"><span data-stu-id="52154-161">Create classes and define paths</span></span>

<span data-ttu-id="52154-162">*Program.cs* 파일 맨 위에 다음 추가 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-162">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="52154-163">최근에 다운로드한 파일의 경로를 포함하고 모델을 저장할 세 개의 전역 변수를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-163">You need to create three global variables to hold the paths to the recently downloaded files and to save the model:</span></span>

* <span data-ttu-id="52154-164">`_datapath`에는 모델을 학습시키는 데 사용되는 데이터 집합의 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="52154-164">`_datapath` has the path to the data set used to train the model.</span></span>
* <span data-ttu-id="52154-165">`_testdatapath`에는 모델을 평가하는 데 사용되는 데이터 집합의 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="52154-165">`_testdatapath` has the path to the data set used to evaluate the model.</span></span>
* <span data-ttu-id="52154-166">`_modelpath`에는 학습된 모델이 저장되는 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="52154-166">`_modelpath` has the path where the trained model is stored.</span></span>

<span data-ttu-id="52154-167">`Main` 바로 위의 줄에 다음 코드를 추가하여 최근에 다운로드한 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-167">Add the following code to the line right above `Main` to specify the recently downloaded files:</span></span>

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="52154-168">다음으로 입력 데이터 및 예측에 대한 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="52154-168">Next, create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="52154-169">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-169">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="52154-170">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *TaxiTrip.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-170">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="52154-171">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-171">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="52154-172">새 파일에 다음 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-172">Add the following `using` statements to the new file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="52154-173">기존 클래스 정의를 제거하고 두 개의 클래스 `TaxiTrip` 및 `TaxiTripFarePrediction`가 있는 다음 코드를 *TaxiTrip.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-173">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

<span data-ttu-id="52154-174">`TaxiTrip`은 입력 데이터 집합 클래스이며 각 데이터 집합 열의 정의를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-174">`TaxiTrip` is the input data set class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="52154-175">모델이 학습된 후에는 `TaxiTripFarePrediction` 클래스가 예측에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="52154-175">The `TaxiTripFarePrediction` class is used for prediction after the model has been trained.</span></span> <span data-ttu-id="52154-176">여기에는 단일 부동(`FareAmount`) 및 `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) 특성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="52154-176">It has a single float (`FareAmount`) and a `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) attribute applied.</span></span>

<span data-ttu-id="52154-177">이제 **Program.cs** 파일로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="52154-177">Now go back to the **Program.cs** file.</span></span> <span data-ttu-id="52154-178">`Main`에서 `Console.WriteLine("Hello World!")`를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="52154-178">In `Main`, replace the `Console.WriteLine("Hello World!")` with the following code:</span></span>

```csharp
PredictionModel<TaxiTrip, TaxiTripFarePrediction> model = Train();
```

<span data-ttu-id="52154-179">`Train` 메서드는 모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="52154-179">The `Train` method trains your model.</span></span> <span data-ttu-id="52154-180">다음 코드를 사용하여 `Main` 바로 아래에서만 해당 함수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="52154-180">Create that function just below `Main`, using the following code:</span></span>

```csharp
public static PredictionModel<TaxiTrip, TaxiTripFarePrediction> Train()
{

}
```

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="52154-181">학습 파이프라인 만들기</span><span class="sxs-lookup"><span data-stu-id="52154-181">Create a learning pipeline</span></span>

<span data-ttu-id="52154-182">학습 파이프라인은 모델을 학습시키는 데 필요한 모든 데이터 및 알고리즘을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-182">The learning pipeline loads all of the data and algorithms necessary to train the model.</span></span> <span data-ttu-id="52154-183">`Train()` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-183">Add the following code into the `Train()` method:</span></span>

```csharp
var pipeline = new LearningPipeline();
```

## <a name="load-and-transform-your-data"></a><span data-ttu-id="52154-184">데이터 로드 및 변환</span><span class="sxs-lookup"><span data-stu-id="52154-184">Load and transform your data</span></span>

<span data-ttu-id="52154-185">그런 다음, 데이터를 파이프라인에 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-185">Next, load your data into the pipeline.</span></span> <span data-ttu-id="52154-186">초기에 만들어진 `_datapath`를 가리키고 .csv 파일의 구분 기호(,)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-186">Point to the `_datapath` created initially and specify the delimiter of the .csv file (,).</span></span> <span data-ttu-id="52154-187">마지막 단계 아래의 `Train()` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-187">Add the following code into the `Train()` method underneath the last step:</span></span>

```csharp
pipeline.Add(new TextLoader(_datapath).CreateFrom<TaxiTrip>(separator:','));
```

<span data-ttu-id="52154-188">생성 중인 코드에서는 밑줄 없이 열을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-188">You'll refer to the columns without the underscores in the code you're creating.</span></span> <span data-ttu-id="52154-189">`ColumnCopier()` 함수를 사용하여 “레이블”이라는 새 열에 `FareAmount` 열을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-189">Copy the `FareAmount` column into a new column called "Label" using the `ColumnCopier()` function.</span></span> <span data-ttu-id="52154-190">이 열은 **레이블**입니다.</span><span class="sxs-lookup"><span data-stu-id="52154-190">This column is the **Label**.</span></span>

```csharp
pipeline.Add(new ColumnCopier(("FareAmount", "Label")));
```

<span data-ttu-id="52154-191">일부 **기능 엔지니어링**을 수행하여 기계 학습에 효과적으로 사용할 수 있도록 데이터를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-191">Conduct some **feature engineering** to transform the data so that it can be used effectively for machine learning.</span></span> <span data-ttu-id="52154-192">모델을 학습시키는 알고리즘에는 **숫자** 기능이 필요합니다. 범주 데이터(`VendorId`, `RateCode` 및 `PaymentType`)를 숫자로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-192">The algorithm that trains the model requires **numeric** features, you transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) into numbers.</span></span> <span data-ttu-id="52154-193">`CategoricalOneHotVectorizer()` 함수는 이러한 각 열의 값에 숫자 키를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-193">The `CategoricalOneHotVectorizer()` function assigns a numeric key to the values in each of these columns.</span></span> <span data-ttu-id="52154-194">이 코드를 추가하여 데이터를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-194">Transform your data by adding this code:</span></span>

```csharp
pipeline.Add(new CategoricalOneHotVectorizer("VendorId",
                                             "RateCode",
                                             "PaymentType"));
```

<span data-ttu-id="52154-195">데이터 준비의 마지막 단계에서는 `ColumnConcatenator()` 함수를 사용하여 모든 **기능**을 하나의 벡터로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-195">The last step in data preparation combines all of your **features** into one vector using the `ColumnConcatenator()` function.</span></span> <span data-ttu-id="52154-196">이 필수 단계를 통해 알고리즘이 기능을 쉽게 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52154-196">This necessary step helps the algorithm easily process your features.</span></span> <span data-ttu-id="52154-197">다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-197">Add the following code:</span></span>

```csharp
pipeline.Add(new ColumnConcatenator("Features",
                                    "VendorId",
                                    "RateCode",
                                    "PassengerCount",
                                    "TripDistance",
                                    "PaymentType"));
```

<span data-ttu-id="52154-198">`trip_time_in_secs` 열이 포함되지 않은 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52154-198">Notice that the `trip_time_in_secs` column isn't included.</span></span> <span data-ttu-id="52154-199">이미 유용한 예측 기능이 아니라고 판단했습니다.</span><span class="sxs-lookup"><span data-stu-id="52154-199">You already determined that it isn't a useful prediction feature.</span></span>

> [!NOTE]
> <span data-ttu-id="52154-200">성공적인 실행을 위해 이러한 단계를 위에 지정된 순서대로 파이프라인에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-200">These steps must be added to Pipeline in the order specified above for successful execution.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="52154-201">학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="52154-201">Choose a learning algorithm</span></span>

<span data-ttu-id="52154-202">파이프라인에 데이터를 추가하고 데이터를 올바른 입력 형식으로 변환한 후 학습 알고리즘(**학습자**)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-202">After adding the data to the pipeline and transforming it into the correct input format, you select a learning algorithm (**learner**).</span></span> <span data-ttu-id="52154-203">학습 알고리즘은 모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="52154-203">The learning algorithm trains the model.</span></span> <span data-ttu-id="52154-204">이 문제에 대해 **회귀 작업**을 선택했으므로 **그라데이션 승격**을 사용하는 파이프라인에 `FastTreeRegressor()` 학습자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-204">You chose a **regression task** for this problem, so you add a learner called `FastTreeRegressor()` to the pipeline that utilizes **gradient boosting**.</span></span>

<span data-ttu-id="52154-205">그라데이션 승격은 회귀 문제에 대한 기계 학습 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="52154-205">Gradient boosting is a machine learning technique for regression problems.</span></span> <span data-ttu-id="52154-206">이 파이프라인은 각 회귀 트리를 단계적으로 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-206">It builds each regression tree in a step-wise fashion.</span></span> <span data-ttu-id="52154-207">미리 정의된 손실 함수를 사용하여 각 단계에서 오류를 측정한 다음, 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-207">It uses a pre-defined loss function to measure the error in each step and correct for it in the next.</span></span> <span data-ttu-id="52154-208">결과는 실제로 더 약한 예측 모델의 앙상블인 예측 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="52154-208">The result is a prediction model that is actually an ensemble of weaker prediction models.</span></span> <span data-ttu-id="52154-209">그라데이션 승격에 대한 자세한 내용은 [Boosted Decision Tree Regression](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression)(승격된 의사 결정 트리 회귀)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52154-209">For more information about gradient boosting, see [Boosted Decision Tree Regression](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).</span></span>

<span data-ttu-id="52154-210">마지막 단계에서 추가된 데이터 처리 코드 다음에 오는 `Train()` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-210">Add the following code into the `Train()` method following the data processing code added in the last step:</span></span>

```csharp
pipeline.Add(new FastTreeRegressor());
```

<span data-ttu-id="52154-211">모든 이전 단계를 개별 문으로 파이프라인에 추가했지만, C#에는 파이프라인을 더 간단하게 만들고 초기화할 수 있는 편리한 컬렉션 초기화 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52154-211">You added all the preceding steps to the pipeline as individual statements, but C# has a handy collection initialization syntax that makes it simpler to create and initialize the pipeline.</span></span> <span data-ttu-id="52154-212">지금까지 `Train()` 메서드에 추가한 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="52154-212">Replace the code you added so far to the `Train()` method with the following code:</span></span>

[!code-csharp[CreatePipeline](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create and initialize the learning pipeline")]

## <a name="train-the-model"></a><span data-ttu-id="52154-213">모델 학습</span><span class="sxs-lookup"><span data-stu-id="52154-213">Train the model</span></span>

<span data-ttu-id="52154-214">마지막 단계에서는 모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="52154-214">The final step is to train the model.</span></span> <span data-ttu-id="52154-215">이 시점까지는 파이프라인에서 아무것도 실행되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="52154-215">Until this point, nothing in the pipeline has been executed.</span></span> <span data-ttu-id="52154-216">`pipeline.Train<T_Input, T_Output>()` 함수는 미리 정의된 `TaxiTrip` 클래스 형식에서 사용되고 `TaxiTripFarePrediction` 형식을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-216">The `pipeline.Train<T_Input, T_Output>()` function takes in the pre-defined `TaxiTrip` class type and outputs a `TaxiTripFarePrediction` type.</span></span> <span data-ttu-id="52154-217">이 마지막 코드 조각을 `Train()` 함수에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-217">Add this final piece of code into the `Train()` function:</span></span>

[!code-csharp[TrainMOdel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Train your model")]

<span data-ttu-id="52154-218">됐습니다!</span><span class="sxs-lookup"><span data-stu-id="52154-218">And that's it!</span></span> <span data-ttu-id="52154-219">NYC에서 택시 요금을 예측할 수 있는 기계 학습 모델을 성공적으로 학습시켰습니다.</span><span class="sxs-lookup"><span data-stu-id="52154-219">You have successfully trained a machine learning model that can predict taxi fares in NYC.</span></span> <span data-ttu-id="52154-220">이제 모델이 얼마나 정확한지 이해하고 모델을 사용하는 방법을 알아보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="52154-220">Now take a look to understand how accurate your model is and learn how to consume it.</span></span>

## <a name="save-the-model"></a><span data-ttu-id="52154-221">모델 저장</span><span class="sxs-lookup"><span data-stu-id="52154-221">Save the model</span></span>

<span data-ttu-id="52154-222">다음 단계로 이동하기 전에 `Train()` 함수의 끝에 다음 코드를 추가하여 모델을 .zip 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-222">Before you go onto the next step, save your model to a .zip file by adding the following code at the end of your `Train()` function:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Save the model asynchronously and return the model")]

<span data-ttu-id="52154-223">`model.WriteAsync()` 호출에 `await` 문을 추가하면 `Train()` 메서드를 `Task`를 반환하는 비동기 메서드로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-223">Adding the `await` statement to the `model.WriteAsync()` call means that the `Train()` method must be changed to an async method that returns a `Task`.</span></span> <span data-ttu-id="52154-224">다음 코드에 표시된 대로 `Train`의 시그니처를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-224">Modify the signature of `Train` as shown in the following code:</span></span>

[!code-csharp[AsyncTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "Make the Train method async and return a task.")]

<span data-ttu-id="52154-225">`Train` 메서드의 반환 형식을 변경하면 다음 코드에 표시된 대로 `Main` 메서드에서 `Train`을 호출하는 코드에 `await`를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-225">Changing the return type of the `Train` method means you have to add an `await` to the code that calls `Train` in the `Main` method as shown in the following code:</span></span>

[!code-csharp[AwaitTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Await the Train method")]

<span data-ttu-id="52154-226">`Main` 메서드에 `await`를 추가하면 `Main` 메서드는 `async` 한정자를 포함하고 `Task`를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-226">Adding an `await` in your `Main` method means the `Main` method must have the `async` modifier and return a `Task`:</span></span>

[!code-csharp[AsyncMain](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Make the Main method async and return a task.")]

<span data-ttu-id="52154-227">또한 파일의 맨 위에 있는 문을 사용하여 다음을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-227">You also need to add the following using statement at the top of the file:</span></span>

[!code-csharp[UsingTasks](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Add System.Threading.Tasks. to your usings.")]

<span data-ttu-id="52154-228">`async Main` 메서드는 C# 7.1의 새로운 기능이고 프로젝트의 기본 언어 버전은 C# 7.0이므로 언어 버전을 C# 7.1 이상으로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-228">Because the `async Main` method is a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="52154-229">이 작업을 하려면 **솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-229">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="52154-230">**빌드** 탭을 선택하고 **고급** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-230">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="52154-231">드롭다운에서 **C# 7.1**(또는 이상 버전)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-231">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="52154-232">**확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-232">Select the **OK** button.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="52154-233">모델 평가</span><span class="sxs-lookup"><span data-stu-id="52154-233">Evaluate the model</span></span>

<span data-ttu-id="52154-234">평가는 모델이 얼마나 잘 작동하는지 확인하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="52154-234">Evaluation is the process of checking how well the model works.</span></span> <span data-ttu-id="52154-235">모델은 학습될 때 사용하지 않은 데이터를 기반으로 적절한 예측을 하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-235">It's important that your model makes good predictions on data that it didn't use when it was trained.</span></span> <span data-ttu-id="52154-236">이를 수행하는 한 가지 방법은 이 자습서에서 한 것처럼 데이터를 학습 및 테스트 데이터 집합으로 분할하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="52154-236">One way to do this is by splitting the data into train and test datasets, as you did in this tutorial.</span></span> <span data-ttu-id="52154-237">학습 데이터를 기반으로 모델을 학습시켰으므로 테스트 데이터에서 모델이 얼마나 잘 작동하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52154-237">Now that you've trained the model on the train data, you can see how well it performs on the test data.</span></span>

<span data-ttu-id="52154-238">`Main` 함수로 돌아가서 `Train()` 메서드 호출 아래에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-238">Go back to your `Main` function and add the following code beneath the call to the `Train()`method:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Evaluate the model.")]

<span data-ttu-id="52154-239">`Evaluate()` 함수는 모델을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-239">The `Evaluate()` function evaluates your model.</span></span> <span data-ttu-id="52154-240">`Train()` 아래에 해당 함수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="52154-240">Create that function below `Train()`.</span></span> <span data-ttu-id="52154-241">다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-241">Add the following code:</span></span>

```csharp
private static void Evaluate(PredictionModel<TaxiTrip, TaxiTripFarePrediction> model)
{

}
```

<span data-ttu-id="52154-242">`TextLoader()` 함수를 사용하여 테스트 데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-242">Load the test data using the `TextLoader()` function.</span></span> <span data-ttu-id="52154-243">`Evaluate()` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-243">Add the following code into the `Evaluate()` method:</span></span>

[!code-csharp[LoadTestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Load the test data.")]

<span data-ttu-id="52154-244">다음 코드를 추가하여 모델을 평가하고 모델에 대한 메트릭을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-244">Add the following code to evaluate the model and produce the metrics for it:</span></span>

[!code-csharp[EvaluateAndMeasure](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Evaluate the model and its predictions.")]

<span data-ttu-id="52154-245">RMS는 회귀 문제를 평가하기 위한 하나의 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="52154-245">RMS is one metric for evaluating regression problems.</span></span> <span data-ttu-id="52154-246">RMS가 낮을수록 모델이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="52154-246">The lower it is, the better your model.</span></span> <span data-ttu-id="52154-247">`Evaluate()` 함수에 다음 코드를 추가하여 모델의 RMS를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-247">Add the following code into the `Evaluate()` function to print the RMS for your model.</span></span>

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Display the RMS metric.")]

<span data-ttu-id="52154-248">RSquared는 회귀 문제를 평가하기 위한 또 다른 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="52154-248">RSquared is another metric for evaluating regression problems.</span></span> <span data-ttu-id="52154-249">RSquared는 0~1 사이의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="52154-249">RSquared will be a value between 0 and 1.</span></span> <span data-ttu-id="52154-250">1에 가까울수록 모델이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="52154-250">The closer you are to 1, the better your model.</span></span> <span data-ttu-id="52154-251">`Evaluate()` 함수에 다음 코드를 추가하여 모델의 RSquared 값을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-251">Add the following code into the `Evaluate()` function to print the RSquared value for your model.</span></span>

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Display the RSquared metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="52154-252">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="52154-252">Use the model for predictions</span></span>

<span data-ttu-id="52154-253">다음으로는 모델이 올바르게 작동하는지 확인하는 데 사용할 수 있는 테스트 시나리오를 수용할 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="52154-253">Next, create a class to house test scenarios that you can use to make sure your model is working correctly:</span></span>

1. <span data-ttu-id="52154-254">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-254">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="52154-255">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *TestTrips.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-255">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestTrips.cs*.</span></span> <span data-ttu-id="52154-256">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-256">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="52154-257">다음 예제처럼 클래스를 static으로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-257">Modify the class to be static like in the following example:</span></span>

[!code-csharp[StaticClass](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#1 "Change class to be a static class.")]

<span data-ttu-id="52154-258">이 자습서에서는 이 클래스 내에서 하나의 테스트 이동을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-258">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="52154-259">나중에 이 샘플로 실험할 다른 시나리오를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52154-259">Later you can add other scenarios to experiment with this sample.</span></span> <span data-ttu-id="52154-260">다음 코드를 `TestTrips` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-260">Add the following code into the `TestTrips` class:</span></span>

[!code-csharp[TestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#2 "Create aq trip to predict its cost.")]

<span data-ttu-id="52154-261">이 이동의 실제 요금은 29.5지만 자리 표시자로 0을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-261">This trip's actual fare is 29.5, but use 0 as a placeholder.</span></span> <span data-ttu-id="52154-262">기계 학습 알고리즘이 요금을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-262">The machine learning algorithm will predict the fare.</span></span>

<span data-ttu-id="52154-263">다음 코드를 `Main` 함수에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-263">Add the following code in your `Main` function.</span></span> <span data-ttu-id="52154-264">`TestTrip` 데이터를 사용하여 모델을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-264">It tests out your model using the `TestTrip` data:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Try a prediction.")]

<span data-ttu-id="52154-265">프로그램을 실행하여 테스트 사례에 대해 예측된 택시 요금을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="52154-265">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="52154-266">지금까지</span><span class="sxs-lookup"><span data-stu-id="52154-266">Congratulations!</span></span> <span data-ttu-id="52154-267">택시 요금 예측을 위한 기계 학습 모델을 성공적으로 빌드하고, 정확도를 평가하고, 모델을 테스트했습니다.</span><span class="sxs-lookup"><span data-stu-id="52154-267">You've now successfully built a machine learning model for predicting taxi fares, evaluated its accuracy, and tested it.</span></span> <span data-ttu-id="52154-268">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52154-268">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="52154-269">다음 단계</span><span class="sxs-lookup"><span data-stu-id="52154-269">Next steps</span></span>

<span data-ttu-id="52154-270">이 자습서에서는 다음 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="52154-270">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="52154-271">문제 이해</span><span class="sxs-lookup"><span data-stu-id="52154-271">Understand the problem</span></span>
> * <span data-ttu-id="52154-272">적절한 기계 학습 작업 선택</span><span class="sxs-lookup"><span data-stu-id="52154-272">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="52154-273">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="52154-273">Prepare and understand your data</span></span>
> * <span data-ttu-id="52154-274">학습 파이프라인 만들기</span><span class="sxs-lookup"><span data-stu-id="52154-274">Create a learning pipeline</span></span>
> * <span data-ttu-id="52154-275">데이터 로드 및 변환</span><span class="sxs-lookup"><span data-stu-id="52154-275">Load and transform your data</span></span>
> * <span data-ttu-id="52154-276">학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="52154-276">Choose a learning algorithm</span></span>
> * <span data-ttu-id="52154-277">모델 학습</span><span class="sxs-lookup"><span data-stu-id="52154-277">Train the model</span></span>
> * <span data-ttu-id="52154-278">모델 평가</span><span class="sxs-lookup"><span data-stu-id="52154-278">Evaluate the model</span></span>
> * <span data-ttu-id="52154-279">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="52154-279">Use the model for predictions</span></span>

<span data-ttu-id="52154-280">학습을 계속하고 더 많은 샘플을 찾으려면 GitHub 리포지토리를 체크 아웃하세요.</span><span class="sxs-lookup"><span data-stu-id="52154-280">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="52154-281">dotnet/machinelearning GitHub 리포지토리</span><span class="sxs-lookup"><span data-stu-id="52154-281">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)
