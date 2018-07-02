---
title: 감정 분석 이진 분류 시나리오에서 ML.NET 사용
description: 감정 예측을 통해 적절한 작업을 수행하는 방법을 이해하기 위해 이진 분류 시나리오에서 ML.NET을 사용하는 방법을 살펴봅니다.
ms.date: 06/04/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 898b4664120b6eeb0ef18aac3acdc94b0ca0bacd
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36314840"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a><span data-ttu-id="abdee-103">자습서: 감정 분석 이진 분류 시나리오에서 ML.NET 사용</span><span class="sxs-lookup"><span data-stu-id="abdee-103">Tutorial: Use ML.NET in a sentiment analysis binary classification scenario</span></span>

> [!NOTE]
> <span data-ttu-id="abdee-104">이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="abdee-105">자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="abdee-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="abdee-106">이 샘플 자습서에서는 ML.NET을 사용하여 Visual Studio 2017에서 C#를 사용하는 .NET Core 콘솔 응용 프로그램을 통해 감정 분류자를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-106">This sample tutorial illustrates using ML.NET to create a sentiment classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="abdee-107">이 자습서에서는 다음 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="abdee-108">문제 이해</span><span class="sxs-lookup"><span data-stu-id="abdee-108">Understand the problem</span></span>
> * <span data-ttu-id="abdee-109">적절한 기계 학습 작업 선택</span><span class="sxs-lookup"><span data-stu-id="abdee-109">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="abdee-110">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="abdee-110">Prepare your data</span></span>
> * <span data-ttu-id="abdee-111">학습 파이프라인 만들기</span><span class="sxs-lookup"><span data-stu-id="abdee-111">Create the learning pipeline</span></span>
> * <span data-ttu-id="abdee-112">분류자 로드</span><span class="sxs-lookup"><span data-stu-id="abdee-112">Load a classifier</span></span>
> * <span data-ttu-id="abdee-113">모델 학습</span><span class="sxs-lookup"><span data-stu-id="abdee-113">Train the model</span></span>
> * <span data-ttu-id="abdee-114">다른 데이터 집합을 사용하여 모델 평가</span><span class="sxs-lookup"><span data-stu-id="abdee-114">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="abdee-115">모델을 사용하여 테스트 데이터 결과 예측</span><span class="sxs-lookup"><span data-stu-id="abdee-115">Predict the test data outcomes with the model</span></span>

## <a name="sentiment-analysis-sample-overview"></a><span data-ttu-id="abdee-116">감정 분석 샘플 개요</span><span class="sxs-lookup"><span data-stu-id="abdee-116">Sentiment analysis sample overview</span></span>

<span data-ttu-id="abdee-117">샘플은 ML.NET을 사용하여 감정을 긍정적 또는 부정적으로 분류하고 예측하는 모델을 학습시키는 콘솔 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-117">The sample is a console app that uses ML.NET to train a model that classifies and predicts sentiment as either positive or negative.</span></span> <span data-ttu-id="abdee-118">또한 품질 분석을 위해 두 번째 데이터 집합을 사용하여 모델을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-118">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="abdee-119">감정 데이터 집합은 WikiDetox 프로젝트에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-119">The sentiment datasets are from the WikiDetox project.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="abdee-120">전제 조건</span><span class="sxs-lookup"><span data-stu-id="abdee-120">Prerequisites</span></span>

* <span data-ttu-id="abdee-121">“.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).</span><span class="sxs-lookup"><span data-stu-id="abdee-121">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="abdee-122">[Wikipedia detox 줄 데이터 탭 구분 파일(wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).</span><span class="sxs-lookup"><span data-stu-id="abdee-122">The [Wikipedia detox line data tab separated file (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).</span></span>
* <span data-ttu-id="abdee-123">[Wikipedia detox 줄 테스트 탭 구분 파일(wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).</span><span class="sxs-lookup"><span data-stu-id="abdee-123">The [Wikipedia detox line test tab separated file (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="abdee-124">기계 학습 워크플로</span><span class="sxs-lookup"><span data-stu-id="abdee-124">Machine learning workflow</span></span>

<span data-ttu-id="abdee-125">이 자습서는 프로세스가 체계적으로 이동할 수 있도록 하는 기계 학습 워크플로를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-125">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="abdee-126">워크플로 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-126">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="abdee-127">**문제 이해**</span><span class="sxs-lookup"><span data-stu-id="abdee-127">**Understand the problem**</span></span>
2. <span data-ttu-id="abdee-128">**데이터 수집**</span><span class="sxs-lookup"><span data-stu-id="abdee-128">**Ingest the data**</span></span>
3. <span data-ttu-id="abdee-129">**데이터 전처리 및 기능 엔지니어링**</span><span class="sxs-lookup"><span data-stu-id="abdee-129">**Data preprocess and feature engineering**</span></span>
4. <span data-ttu-id="abdee-130">**모델 학습 및 예측**</span><span class="sxs-lookup"><span data-stu-id="abdee-130">**Train and predict the model**</span></span>
5. <span data-ttu-id="abdee-131">**모델 평가**</span><span class="sxs-lookup"><span data-stu-id="abdee-131">**Evaluate the model**</span></span>
6. <span data-ttu-id="abdee-132">**모델 연산화**</span><span class="sxs-lookup"><span data-stu-id="abdee-132">**Model operationalization**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="abdee-133">문제 이해</span><span class="sxs-lookup"><span data-stu-id="abdee-133">Understand the problem</span></span>

<span data-ttu-id="abdee-134">먼저 문제를 이해해야 하므로 모델 빌드 및 학습을 지원할 수 있는 부분으로 문제를 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-134">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="abdee-135">문제를 구분하여 결과를 예측하고 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-135">Breaking the problem down you to predict and evaluate the results.</span></span>

<span data-ttu-id="abdee-136">이 자습서의 문제는 들어오는 웹 사이트 댓글 감정을 이해하여 적절한 작업을 수행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-136">The problem for this tutorial is to understand incoming website comment sentiment to take the appropriate action.</span></span>

<span data-ttu-id="abdee-137">모델 학습에 사용할 데이터의 감정 텍스트와 감정 값 및 평가 후 조작에 사용할 수 있는 예측 감정 값으로 문제를 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-137">You can break down the problem to the sentiment text and sentiment value for the data you want to train the model with, and a predicted sentiment value that you can evaluate and then use operationally.</span></span>

<span data-ttu-id="abdee-138">그런 다음, 기계 학습 작업 선택에 도움이 되는 감정을 **확인**해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-138">You then need to **determine** the sentiment, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="abdee-139">적절한 기계 학습 작업 선택</span><span class="sxs-lookup"><span data-stu-id="abdee-139">Select the appropriate machine learning task</span></span>

<span data-ttu-id="abdee-140">이 문제에서 다음 사실을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-140">With this problem, you know the following facts:</span></span>

<span data-ttu-id="abdee-141">학습 데이터: 웹 사이트 댓글은 긍정적 또는 부정적(**감정**)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-141">Training data: website comments can be positive or negative (**sentiment**).</span></span>
<span data-ttu-id="abdee-142">다음 예제와 같이 새로운 웹 사이트 댓글의 **감정**을 긍정적 또는 부정적으로 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-142">Predict the **sentiment** of a new website comment, either positive or negative, such as in the following examples:</span></span>

* <span data-ttu-id="abdee-143">Wikipedia에 의미 없는 내용을 추가하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="abdee-143">Please refrain from adding nonsense to Wikipedia.</span></span>
* <span data-ttu-id="abdee-144">그는 최고이고 기사에 이 내용이 언급되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-144">He is the best, and the article should say that.</span></span>

<span data-ttu-id="abdee-145">분류 기계 학습 작업이 이 시나리오에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-145">The classification machine learning task is best suited for this scenario.</span></span>

### <a name="about-the-classification-task"></a><span data-ttu-id="abdee-146">분류 작업 정보</span><span class="sxs-lookup"><span data-stu-id="abdee-146">About the classification task</span></span>

<span data-ttu-id="abdee-147">분류는 데이터를 사용하여 데이터 항목 또는 행의 범주, 형식 또는 클래스를 **확인**하는 기계 학습 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-147">Classification is a machine learning task that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="abdee-148">예를 들어 분류를 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-148">For example, you can use classification to:</span></span>

* <span data-ttu-id="abdee-149">감정을 긍정적 또는 부정적으로 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-149">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="abdee-150">전자 메일을 스팸, 정크 또는 정상으로 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-150">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="abdee-151">환자의 실험실 샘플이 종양성인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-151">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="abdee-152">영업 캠페인에 응답하는 고객의 성향을 기준으로 고객을 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-152">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="abdee-153">일반적으로 분류 작업은 다음 형식 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-153">Classification tasks are frequently one of the following types:</span></span>

* <span data-ttu-id="abdee-154">이진: A 또는 B.</span><span class="sxs-lookup"><span data-stu-id="abdee-154">Binary: either A or B.</span></span>
* <span data-ttu-id="abdee-155">다중 클래스: 단일 모델을 사용하여 예측할 수 있는 여러 범주.</span><span class="sxs-lookup"><span data-stu-id="abdee-155">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="abdee-156">콘솔 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="abdee-156">Create a console application</span></span>

1. <span data-ttu-id="abdee-157">Visual Studio 2017을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-157">Open Visual Studio 2017.</span></span> <span data-ttu-id="abdee-158">메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-158">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="abdee-159">*새 프로젝트*\* 대화 상자에서 **Visual C#** 노드와 **.NET Core** 노드를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-159">In the *New Project*\* dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="abdee-160">그런 다음 **콘솔 앱(.NET Core)** 프로젝트 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-160">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="abdee-161">**이름** 텍스트 상자에 “SentimentAnalysis”를 입력한 다음, **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-161">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="abdee-162">프로젝트에서 *Data* 디렉터리를 만들어 데이터 집합 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-162">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="abdee-163">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 폴더**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-163">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="abdee-164">“Data”를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-164">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="abdee-165">**Microsoft.ML NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-165">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="abdee-166">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-166">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="abdee-167">“nuget.org”를 패키지 소스로 선택하고, [찾아보기] 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-167">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="abdee-168">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-168">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="abdee-169">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="abdee-169">Prepare your data</span></span>

1. <span data-ttu-id="abdee-170">[WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) 및 [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) 데이터 집합을 다운로드하여 이전에 만든 *Data* 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-170">Download the [WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) and the [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="abdee-171">첫 번째 데이터 집합은 기계 학습 모델을 교육하고 두 번째 데이터 집합은 모델이 얼마나 정확한지 평가하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-171">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="abdee-172">솔루션 탐색기에서 각 \*.tsv 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-172">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="abdee-173">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **항상**으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-173">Under **Advanced**, change the value of **Copy to Output Directory** to **Always**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="abdee-174">클래스 만들기 및 경로 정의</span><span class="sxs-lookup"><span data-stu-id="abdee-174">Create classes and define paths</span></span>

<span data-ttu-id="abdee-175">*Program.cs* 파일 맨 위에 다음 추가 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-175">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="abdee-176">최근에 다운로드한 파일의 경로를 포함할 세 개의 전역 변수를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-176">You need to create three global variables to hold the path to the recently downloaded files:</span></span>

* <span data-ttu-id="abdee-177">`_dataPath`에는 모델을 학습시키는 데 사용되는 데이터 집합의 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-177">`_dataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="abdee-178">`_testDataPath`에는 모델을 평가하는 데 사용되는 데이터 집합의 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-178">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="abdee-179">`_modelPath`에는 학습된 모델이 저장되는 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-179">`_modelPath` has the path where the trained model is saved.</span></span>

<span data-ttu-id="abdee-180">`Main` 메서드 바로 위의 줄에 다음 코드를 추가하여 최근에 다운로드한 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-180">Add the following code to the line right above the `Main` method to specify the recently downloaded files:</span></span>

[!code-csharp[Declare file variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#2 "Declare variables to store data files")]

<span data-ttu-id="abdee-181">입력 데이터 및 예측에 대한 일부 클래스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-181">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="abdee-182">새 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-182">Add a new class to your project:</span></span>

1. <span data-ttu-id="abdee-183">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-183">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="abdee-184">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *SentimentData.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-184">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="abdee-185">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-185">Then, select the **Add** button.</span></span>

    <span data-ttu-id="abdee-186">*SentimentData.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-186">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="abdee-187">다음 `using` 문을 *SentimentData.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-187">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#1 "Add necessary usings")]

<span data-ttu-id="abdee-188">기존 클래스 정의를 제거하고 두 개의 클래스 `SentimentData` 및 `SentimentPrediction`가 있는 다음 코드를 *SentimentData.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-188">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#2 "Declare data record types")]

<span data-ttu-id="abdee-189">`SentimentData`는 입력 데이터 집합 클래스이며 긍정적 또는 부정적 감정 값을 가진 `float`(`Sentiment`) 및 댓글 문자열(`SentimentText`)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-189">`SentimentData` is the input dataset class and has a `float` (`Sentiment`) that has a value for sentiment of either positive or negative, and a string for the comment (`SentimentText`).</span></span> <span data-ttu-id="abdee-190">두 필드에 모두 `Column` 특성이 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-190">Both fields have `Column` attributes attached to them.</span></span> <span data-ttu-id="abdee-191">이 특성은 데이터 파일의 각 필드 순서와 어떤 것이 `Label` 필드인지 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-191">This attribute describes the order of each field in the data file, and which is the `Label` field.</span></span> <span data-ttu-id="abdee-192">`SentimentPrediction`은 모델이 학습된 후 예측에 사용되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-192">`SentimentPrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="abdee-193">여기에는 단일 부울(`Sentiment`)과 `PredictedLabel` `ColumnName` 특성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-193">It has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="abdee-194">`Label`은 모델을 만들고 학습시키는 데 사용되며 두 번째 데이터 집합과 함께 모델을 평가하는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-194">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="abdee-195">`PredictedLabel`은 예측 및 평가 중에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-195">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="abdee-196">평가를 위해 학습 데이터가 있는 입력, 예측 값 및 모델이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-196">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="abdee-197">*Program.cs* 파일에서 다음 예제와 같이 `void`를 `async Task`로 바꿔 `Main` 메서드 시그니처를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-197">In the *Program.cs* file, change the `Main` method signature by replacing `void` with `async Task`, as in the following example:</span></span>

```csharp
static async Task Main(string[] args) 
{

}
```

<span data-ttu-id="abdee-198">나중에 모델을 zip 파일로 저장할 것이고 해당 외부 작업이 완료될 때까지 프로그램이 대기해야 하므로 <xref:System.Threading.Tasks.Task> 반환 형식을 사용하여 `async`를 `Main`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-198">You add `async` to `Main` with a <xref:System.Threading.Tasks.Task> return type because you're saving the model to a zip file later, and the program needs to wait until that external task completes.</span></span>

> [!NOTE]
> <span data-ttu-id="abdee-199">*비동기 기본* 메서드를 통해 `Main` 메서드에서 `await`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-199">An *async main* method enables you to use `await` in your `Main` method.</span></span> <span data-ttu-id="abdee-200">자세한 내용은 C# 프로그래밍 가이드의 [async main](../../../docs/csharp/programming-guide/main-and-command-args/index.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="abdee-200">For more information, see the [async main](../../../docs/csharp/programming-guide/main-and-command-args/index.md) topic in the C# programming guide.</span></span>

<span data-ttu-id="abdee-201">`Main` 메서드에서 `Console.WriteLine("Hello World!")` 줄을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-201">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[Train](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#3 "Train your model")]

<span data-ttu-id="abdee-202">`Train` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-202">The `Train` method executes the following tasks:</span></span>

* <span data-ttu-id="abdee-203">데이터를 로드 또는 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-203">Loads or ingests the data.</span></span>
* <span data-ttu-id="abdee-204">데이터를 전처리 및 기능화합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-204">Preprocesses and featurizes the data.</span></span>
* <span data-ttu-id="abdee-205">모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-205">Trains the model.</span></span>
* <span data-ttu-id="abdee-206">테스트 데이터를 기반으로 감정을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-206">Predicts sentiment based on test data.</span></span>

<span data-ttu-id="abdee-207">다음 코드를 사용하여 `Main` 메서드 바로 뒤에 `Train` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-207">Create the `Train` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static async Task<PredictionModel<SentimentData, SentimentPrediction>> Train()
{

}
```

## <a name="ingest-the-data"></a><span data-ttu-id="abdee-208">데이터 수집</span><span class="sxs-lookup"><span data-stu-id="abdee-208">Ingest the data</span></span>

<span data-ttu-id="abdee-209">데이터 로드, 데이터 처리/기능화 및 모델을 포함할 <xref:Microsoft.ML.LearningPipeline>의 새 인스턴스를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-209">Initialize a new instance of <xref:Microsoft.ML.LearningPipeline> that will include the data loading, data processing/featurization, and model.</span></span> <span data-ttu-id="abdee-210">다음 코드를 `Train` 메서드의 첫 번째 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-210">Add the following code as the first line of the `Train` method:</span></span>

[!code-csharp[LearningPipeline](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#5 "Create a learning pipeline")]

<span data-ttu-id="abdee-211"><xref:Microsoft.ML.Data.TextLoader> 개체는 파이프라인의 첫 번째 부분이며 학습 파일 데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-211">The <xref:Microsoft.ML.Data.TextLoader> object is the first part of the pipeline, and loads the training file data.</span></span>

[!code-csharp[TextLoader](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#6 "Add a text loader to the pipeline")]

## <a name="data-preprocess-and-feature-engineering"></a><span data-ttu-id="abdee-212">데이터 전처리 및 기능 엔지니어링</span><span class="sxs-lookup"><span data-stu-id="abdee-212">Data preprocess and feature engineering</span></span>

<span data-ttu-id="abdee-213">데이터 전처리 및 정리는 데이터 집합이 기계 학습에 효과적으로 사용되기 전에 수행되는 중요한 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-213">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="abdee-214">원시 데이터는 종종 정리되지 않고 불안정하며 값이 누락될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-214">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="abdee-215">이러한 모델링 작업 없이 데이터를 사용하면 잘못된 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-215">Using data without these modeling tasks can produce misleading results.</span></span> <span data-ttu-id="abdee-216">ML.NET의 변환 파이프라인을 사용하면 학습 또는 테스트 전에 데이터에 적용되는 사용자 지정 변환 집합을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-216">ML.NET's transform pipelines allow you to compose a custom set of transforms that are applied to your data before training or testing.</span></span> <span data-ttu-id="abdee-217">변환의 기본 목적은 데이터 기능화입니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-217">The transforms' primary purpose is for data featurization.</span></span> <span data-ttu-id="abdee-218">변환 파이프라인의 장점은 변환 파이프라인 정의 후에 파이프라인을 저장하여 테스트 데이터에 적용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-218">A transform pipeline's advantage is that after transform pipeline definition, save the pipeline to apply it to test data.</span></span>

<span data-ttu-id="abdee-219"><xref:Microsoft.ML.Transforms.TextFeaturizer>를 적용하여 `SentimentText` 열을 기계 학습 알고리즘에 사용되는 `Features`라는 [숫자 벡터](../resources/glossary.md#numerical-feature-vector)로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-219">Apply a <xref:Microsoft.ML.Transforms.TextFeaturizer> to convert the `SentimentText` column into a [numeric vector](../resources/glossary.md#numerical-feature-vector) called `Features` used by the machine learning algorithm.</span></span> <span data-ttu-id="abdee-220">이것이 전처리/기능화 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-220">This is the preprocessing/featurization step.</span></span> <span data-ttu-id="abdee-221">ML.NET에서 사용 가능한 추가 구성 요소를 사용하면 모델에서 더 나은 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-221">Using additional components available in ML.NET can enable better results with your model.</span></span> <span data-ttu-id="abdee-222">`TextFeaturizer`를 다음 코드 줄로 파이프라인에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-222">Add `TextFeaturizer` to the pipeline as the next line of code:</span></span>

[!code-csharp[TextFeaturizer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#7 "Add a TextFeaturizer to the pipeline")]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="abdee-223">학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="abdee-223">Choose a learning algorithm</span></span>

<span data-ttu-id="abdee-224"><xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier> 개체는 이 파이프라인에서 사용할 의사 결정 트리 학습자입니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-224">The <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier> object is a decision tree learner you'll use in this pipeline.</span></span> <span data-ttu-id="abdee-225">기능화 단계와 비슷하게 ML.NET에서 사용 가능한 다양한 학습자를 시도하고 매개 변수를 변경하면 다른 결과가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-225">Similar to the featurization step, trying out different learners available in ML.NET and changing their parameters leads to different results.</span></span> <span data-ttu-id="abdee-226">튜닝의 경우 <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumTrees>, <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumLeaves> 및 <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.MinDocumentsInLeafs> 같은 [하이퍼 매개 변수](../resources/glossary.md#hyperparameter)를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-226">For tuning, you can set [hyperparameters](../resources/glossary.md#hyperparameter) like <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumTrees>, <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumLeaves>, and <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.MinDocumentsInLeafs>.</span></span> <span data-ttu-id="abdee-227">이러한 하이퍼 매개 변수는 모델에 영향을 주기 전에 설정되며 모델별로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-227">These hyperparameters are set before anything affects the model and are model-specific.</span></span> <span data-ttu-id="abdee-228">성능을 위해 의사 결정 트리를 튜닝하는 데 사용되므로 값이 클수록 성능에 부정적인 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-228">They're used to tune the decision tree for performance, so larger values can negatively impact performance.</span></span>

<span data-ttu-id="abdee-229">`Train` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-229">Add the following code to the `Train` method:</span></span>

[!code-csharp[BinaryClassifier](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#8 "Add a fast binary tree classifier")]

## <a name="train-the-model"></a><span data-ttu-id="abdee-230">모델 학습</span><span class="sxs-lookup"><span data-stu-id="abdee-230">Train the model</span></span>

<span data-ttu-id="abdee-231">로드되고 변환된 데이터 집합을 기반으로 <xref:Microsoft.ML.PredictionModel%602> 모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-231">You train the model, <xref:Microsoft.ML.PredictionModel%602>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="abdee-232">`pipeline.Train<SentimentData, SentimentPrediction>()`은 파이프라인을 학습시킵니다(데이터를 로드하고 기능화기 및 학습자를 학습시킴).</span><span class="sxs-lookup"><span data-stu-id="abdee-232">`pipeline.Train<SentimentData, SentimentPrediction>()` trains the pipeline (loads the data, trains the featurizer and learner).</span></span> <span data-ttu-id="abdee-233">이 문제가 발생할 때까지 실험이 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-233">The experiment is not executed until this happens.</span></span>

<span data-ttu-id="abdee-234">`Train` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-234">Add the following code to the `Train` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#9 "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="abdee-235">평가에 사용하기 위해 학습된 모델 저장 및 반환</span><span class="sxs-lookup"><span data-stu-id="abdee-235">Save and Return the model trained to use for evaluation</span></span>

<span data-ttu-id="abdee-236">이 시점에 기존 또는 새 .NET 응용 프로그램에 통합할 수 있는 모델이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-236">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="abdee-237">반환하기 전에 모델을 .zip 파일로 저장하려면 다음 코드를 `Train`의 다음 줄에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-237">To save your model to a .zip file before returning, add the following code to the next line in `Train`:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#10 "Save the model")]

<span data-ttu-id="abdee-238">`Train` 메서드의 끝에 모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-238">Return the model at the end of the `Train` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#11 "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="abdee-239">모델 평가</span><span class="sxs-lookup"><span data-stu-id="abdee-239">Evaluate the model</span></span>

<span data-ttu-id="abdee-240">이제 모델을 만들고 학습시켰으므로 품질 보증 및 유효성 검사를 위해 다른 데이터 집합을 사용하여 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-240">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="abdee-241">`Evaluate` 메서드에서는 `Train`에서 만들어진 모델을 전달하여 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-241">In the `Evaluate` method, the model created in `Train` is passed in to be evaluated.</span></span> <span data-ttu-id="abdee-242">다음 코드와 같이 `Train` 바로 뒤에 `Evaluate` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-242">Create the `Evaluate` method, just after `Train`, as in the following code:</span></span>

```csharp
public static void Evaluate(PredictionModel<SentimentData, SentimentPrediction> model)
{

}
```

<span data-ttu-id="abdee-243">`Evaluate` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-243">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="abdee-244">테스트 데이터 집합을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-244">Loads the test dataset.</span></span>
* <span data-ttu-id="abdee-245">이진 평가자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-245">Creates the binary evaluator.</span></span>
* <span data-ttu-id="abdee-246">모델을 평가하고 메트릭을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-246">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="abdee-247">메트릭을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-247">Displays the metrics.</span></span>

<span data-ttu-id="abdee-248">다음 코드를 사용하여 `Train` 메서드 호출 바로 아래에 `Main` 메서드의 새 메서드 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-248">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#12 "Call the Evaluate method")]

<span data-ttu-id="abdee-249"><xref:Microsoft.ML.Data.TextLoader> 클래스는 동일한 스키마를 사용하여 새 테스트 데이터 집합을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-249">The <xref:Microsoft.ML.Data.TextLoader> class loads the new test dataset with the same schema.</span></span> <span data-ttu-id="abdee-250">이 데이터 집합을 품질 검사로 사용하여 모델을 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-250">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="abdee-251">`Evaluate` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-251">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadText](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#13 "Load the test dataset")]

<span data-ttu-id="abdee-252"><xref:Microsoft.ML.Models.BinaryClassificationEvaluator> 개체는 지정된 데이터 집합을 사용하여 `PredictionModel`에 대한 품질 메트릭을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-252">The <xref:Microsoft.ML.Models.BinaryClassificationEvaluator> object computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="abdee-253">해당 메트릭을 확인하려면 다음 코드를 사용하여 `Evaluate` 메서드의 다음 줄로 평가자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-253">To see those metrics, add the evaluator as the next line in the `Evaluate` method, with the following code:</span></span>

[!code-csharp[BinaryEvaluator](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#14 "Create the binary evaluator")]

<span data-ttu-id="abdee-254"><xref:Microsoft.ML.Models.BinaryClassificationMetrics>에는 이진 분류 평가자가 계산한 전체 메트릭이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-254">The <xref:Microsoft.ML.Models.BinaryClassificationMetrics> contains the overall metrics computed by binary classification evaluators.</span></span> <span data-ttu-id="abdee-255">모델의 품질을 확인하기 위해 이러한 메트릭을 표시하려면 먼저 메트릭을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-255">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="abdee-256">다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-256">Add the following code:</span></span>

[!code-csharp[CreateMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#15 "Evaluate the model and create metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="abdee-257">모델 유효성 검사를 위해 메트릭 표시</span><span class="sxs-lookup"><span data-stu-id="abdee-257">Displaying the metrics for model validation</span></span>

<span data-ttu-id="abdee-258">다음 코드를 사용하여 메트릭을 표시하고, 결과를 공유한 다음, 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-258">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#16 "Display selected metrics")]

## <a name="predict-the-test-data-outcomes-with-the-model"></a><span data-ttu-id="abdee-259">모델을 사용하여 테스트 데이터 결과 예측</span><span class="sxs-lookup"><span data-stu-id="abdee-259">Predict the test data outcomes with the model</span></span>

<span data-ttu-id="abdee-260">다음 코드를 사용하여 `Evaluate` 메서드 바로 뒤에 `Predict` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-260">Create the `Predict` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
public static void Predict(PredictionModel<SentimentData, SentimentPrediction> model)
{

}
```

<span data-ttu-id="abdee-261">`Predict` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-261">The `Predict` method executes the following tasks:</span></span>

* <span data-ttu-id="abdee-262">테스트 데이터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-262">Creates test data.</span></span>
* <span data-ttu-id="abdee-263">테스트 데이터를 기반으로 감정을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-263">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="abdee-264">보고를 위해 테스트 데이터 및 예측을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-264">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="abdee-265">예측 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-265">Displays the predicted results.</span></span>

<span data-ttu-id="abdee-266">다음 코드를 사용하여 `Evaluate` 메서드 호출 바로 아래에 `Main` 메서드의 새 메서드 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-266">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#17 "Call the Predict method")]

<span data-ttu-id="abdee-267">몇몇 댓글을 추가하여 `Predict` 메서드에서 학습된 모델의 예측을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-267">Add some comments to test the trained model's predictions in the `Predict` method:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#18 "Create test data for predictions")]

<span data-ttu-id="abdee-268">이제 모델이 있으므로 <xref:Microsoft.ML.PredictionModel.Predict%2A?displayProperty=nameWithType> 메서드를 사용하여 댓글 데이터의 긍정적 또는 부정적 감정을 예측하는 데 모델을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-268">Now that you have a model, you can use that to predict the positive or negative sentiment of the comment data using the <xref:Microsoft.ML.PredictionModel.Predict%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="abdee-269">예측을 가져오려면 새 데이터에서 `Predict`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-269">To get a prediction, use `Predict` on new data.</span></span> <span data-ttu-id="abdee-270">입력 데이터는 문자열이고 모델은 기능화를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-270">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="abdee-271">파이프라인은 학습 및 예측 중에 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-271">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="abdee-272">특별히 예측을 위해 전처리/기능화 코드를 작성할 필요가 없고 동일한 API가 배치 및 일회성 예측을 둘 다 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-272">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#19 "Create predictions of sentiments")]

### <a name="model-operationalization-prediction"></a><span data-ttu-id="abdee-273">모델 연산화: 예측</span><span class="sxs-lookup"><span data-stu-id="abdee-273">Model operationalization: prediction</span></span>

<span data-ttu-id="abdee-274">결과를 공유하고 이에 따라 작업을 수행하기 위해 `SentimentText` 및 해당 감정 예측을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-274">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="abdee-275">이것을 반환된 데이터를 운영 정책의 일부로 사용하는 연산화라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-275">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="abdee-276">다음 <xref:System.Console.WriteLine?displayProperty=nameWithType> 코드를 사용하여 결과에 대한 헤더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-276">Create a header for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#20 "Display prediction outputs")]

<span data-ttu-id="abdee-277">예측 결과를 표시하기 전에 감정과 예측을 결합하여 예측된 감정이 있는 원래 주석을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-277">Before displaying the predicted results, combine the sentiment and prediction together to see the original comment with its predicted sentiment.</span></span> <span data-ttu-id="abdee-278">다음 코드는 <xref:System.Linq.Enumerable.Zip%2A> 메서드를 사용하여 작업이 수행되도록 하므로, 다음으로 해당 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-278">The following code uses the <xref:System.Linq.Enumerable.Zip%2A> method to make that happen, so add that code next:</span></span>

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#21 "Build the pairs of sentiment data and predictions")]

<span data-ttu-id="abdee-279">이제 `SentimentText` 및 `Sentiment`를 클래스로 결합했으므로 <xref:System.Console.WriteLine?displayProperty=nameWithType> 메서드를 사용하여 결과를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-279">Now that you've combined the `SentimentText` and `Sentiment` into a class, you can display the results using the <xref:System.Console.WriteLine?displayProperty=nameWithType> method:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#22 "Display the predictions")]

<span data-ttu-id="abdee-280">유추된 튜플 요소 이름은 C# 7.1의 새로운 기능이고 프로젝트의 기본 언어 버전은 C# 7.0이므로 언어 버전을 C# 7.1 이상으로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-280">Because inferred tuple element names are a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="abdee-281">이 작업을 하려면 **솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-281">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="abdee-282">**빌드** 탭을 선택하고 **고급** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-282">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="abdee-283">드롭다운에서 **C# 7.1**(또는 이상 버전)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-283">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="abdee-284">**확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-284">Select the **OK** button.</span></span>

## <a name="results"></a><span data-ttu-id="abdee-285">결과</span><span class="sxs-lookup"><span data-stu-id="abdee-285">Results</span></span>

<span data-ttu-id="abdee-286">다음과 같은 결과가 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-286">Your results should be similar to the following.</span></span> <span data-ttu-id="abdee-287">파이프라인이 처리할 때 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-287">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="abdee-288">경고 또는 메시지 처리를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-288">You may see warnings, or processing messages.</span></span> <span data-ttu-id="abdee-289">이해하기 쉽도록 이러한 결과는 다음 결과에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-289">These have been removed from the following results for clarity.</span></span>

```

PredictionModel quality metrics evaluation
------------------------------------------
Accuracy: 66.67%
Auc: 94.44%
F1Score: 75.00%

Sentiment Predictions
---------------------
Sentiment: Please refrain from adding nonsense to Wikipedia. | Prediction: Negative
Sentiment: He is the best, and the article should say that. | Prediction: Positive

```

<span data-ttu-id="abdee-290">지금까지</span><span class="sxs-lookup"><span data-stu-id="abdee-290">Congratulations!</span></span> <span data-ttu-id="abdee-291">이제 메시지 감정을 분류하고 예측하기 위한 기계 학습 모델을 성공적으로 빌드했습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-291">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span> <span data-ttu-id="abdee-292">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-292">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="abdee-293">다음 단계</span><span class="sxs-lookup"><span data-stu-id="abdee-293">Next steps</span></span>

<span data-ttu-id="abdee-294">이 자습서에서는 다음 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="abdee-294">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="abdee-295">문제 이해</span><span class="sxs-lookup"><span data-stu-id="abdee-295">Understand the problem</span></span>
> * <span data-ttu-id="abdee-296">적절한 기계 학습 작업 선택</span><span class="sxs-lookup"><span data-stu-id="abdee-296">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="abdee-297">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="abdee-297">Prepare your data</span></span>
> * <span data-ttu-id="abdee-298">학습 파이프라인 만들기</span><span class="sxs-lookup"><span data-stu-id="abdee-298">Create the learning pipeline</span></span>
> * <span data-ttu-id="abdee-299">분류자 로드</span><span class="sxs-lookup"><span data-stu-id="abdee-299">Load a classifier</span></span>
> * <span data-ttu-id="abdee-300">모델 학습</span><span class="sxs-lookup"><span data-stu-id="abdee-300">Train the model</span></span>
> * <span data-ttu-id="abdee-301">다른 데이터 집합을 사용하여 모델 평가</span><span class="sxs-lookup"><span data-stu-id="abdee-301">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="abdee-302">모델을 사용하여 테스트 데이터 결과 예측</span><span class="sxs-lookup"><span data-stu-id="abdee-302">Predict the test data outcomes with the model</span></span>

<span data-ttu-id="abdee-303">다음 자습서로 이동하여 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="abdee-303">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="abdee-304">택시 요금 예측기</span><span class="sxs-lookup"><span data-stu-id="abdee-304">Taxi Fare Predictor</span></span>](taxi-fare.md)
