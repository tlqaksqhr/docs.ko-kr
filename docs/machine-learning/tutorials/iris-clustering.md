---
title: ML.NET을 사용하여 아이리스 꽃 클러스터(클러스터링)
description: 클러스터링 시나리오에서 ML.NET을 사용하는 방법 알아보기
author: pkulikov
ms.author: johalex
ms.date: 07/02/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 46db9dc7ff425c483f1a9f61da5e806e598b16d5
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37937168"
---
# <a name="tutorial-use-mlnet-to-cluster-iris-flowers-clustering"></a><span data-ttu-id="6ca07-103">자습서: ML.NET을 사용하여 아이리스 꽃 클러스터(클러스터링)</span><span class="sxs-lookup"><span data-stu-id="6ca07-103">Tutorial: Use ML.NET to cluster iris flowers (clustering)</span></span>

> [!NOTE]
> <span data-ttu-id="6ca07-104">이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="6ca07-105">자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ca07-105">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="6ca07-106">이 자습서에서는 ML.NET을 사용하여 [아이리스 꽃 데이터 집합](https://en.wikipedia.org/wiki/Iris_flower_data_set)을 위해 [클러스터링 모델](../resources/tasks.md#clustering)을 빌드하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-106">This tutorial illustrates how to use ML.NET to build a [clustering model](../resources/tasks.md#clustering) for the [iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span></span>

<span data-ttu-id="6ca07-107">이 자습서에서는 다음 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="6ca07-108">문제 이해</span><span class="sxs-lookup"><span data-stu-id="6ca07-108">Understand the problem</span></span>
> - <span data-ttu-id="6ca07-109">적절한 기계 학습 작업 선택</span><span class="sxs-lookup"><span data-stu-id="6ca07-109">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="6ca07-110">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="6ca07-110">Prepare the data</span></span>
> - <span data-ttu-id="6ca07-111">데이터 로드 및 변환</span><span class="sxs-lookup"><span data-stu-id="6ca07-111">Load and transform the data</span></span>
> - <span data-ttu-id="6ca07-112">학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="6ca07-112">Choose a learning algorithm</span></span>
> - <span data-ttu-id="6ca07-113">모델 학습</span><span class="sxs-lookup"><span data-stu-id="6ca07-113">Train the model</span></span>
> - <span data-ttu-id="6ca07-114">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="6ca07-114">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6ca07-115">전제 조건</span><span class="sxs-lookup"><span data-stu-id="6ca07-115">Prerequisites</span></span>

- <span data-ttu-id="6ca07-116">“.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).</span><span class="sxs-lookup"><span data-stu-id="6ca07-116">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="6ca07-117">문제 이해</span><span class="sxs-lookup"><span data-stu-id="6ca07-117">Understand the problem</span></span>

<span data-ttu-id="6ca07-118">이 문제는 꽃 특징을 기반으로 아이리스 꽃 집합을 여러 그룹으로 나누는 것에 관한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-118">This problem is about dividing the set of iris flowers in different groups based on the flower features.</span></span> <span data-ttu-id="6ca07-119">그 특징은 꽃받침의 길이 및 너비와 꽃잎의 길이 및 너비입니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-119">Those features are the length and width of a sepal and the length and width of a petal.</span></span> <span data-ttu-id="6ca07-120">이 자습서에서는 각 꽃 유형이 알려지지 않은 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-120">For this tutorial, assume that the type of each flower is unknown.</span></span> <span data-ttu-id="6ca07-121">특정으로부터 데이터 집합의 구조를 파악하고 데이터 인스턴스가 이 구조에 어떻게 맞는지 예측해보려 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-121">You want to learn the structure of a data set from the features and predict how a data instance fits this structure.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="6ca07-122">적절한 기계 학습 작업 선택</span><span class="sxs-lookup"><span data-stu-id="6ca07-122">Select the appropriate machine learning task</span></span>

<span data-ttu-id="6ca07-123">각 꽃이 속한 그룹을 모르기 때문에 [감독되지 않는 기계 학습](../resources/glossary.md#unsupervised-machine-learning) 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-123">As you don't know to which group each flower belongs to, you choose the [unsupervised machine learning](../resources/glossary.md#unsupervised-machine-learning) task.</span></span> <span data-ttu-id="6ca07-124">같은 그룹의 요소를 다른 그룹의 요소보다 더 서로 유사한 방식으로 그룹의 데이터 집합을 나누려면 [클러스터링](../resources/tasks.md#clustering) 기계 학습 작업을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-124">To divide a data set in groups in such a way that elements in the same group are more similar to each other than to those in other groups, use a [clustering](../resources/tasks.md#clustering) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="6ca07-125">콘솔 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="6ca07-125">Create a console application</span></span>

1. <span data-ttu-id="6ca07-126">Visual Studio 2017을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-126">Open Visual Studio 2017.</span></span> <span data-ttu-id="6ca07-127">메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-127">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="6ca07-128">**새 프로젝트** 대화 상자에서 **Visual C#** 노드와 **.NET Core** 노드를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-128">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="6ca07-129">그런 다음 **콘솔 앱(.NET Core)** 프로젝트 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-129">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="6ca07-130">**이름** 텍스트 상자에 "IrisClustering"을 입력한 다음, **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-130">In the **Name** text box, type "IrisClustering" and then select the **OK** button.</span></span>

1. <span data-ttu-id="6ca07-131">프로젝트에서 *Data* 디렉터리를 만들어 데이터 집합과 모델 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-131">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="6ca07-132">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 폴더**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-132">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="6ca07-133">“Data”를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-133">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="6ca07-134">**Microsoft.ML** NuGet 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-134">Install the **Microsoft.ML** NuGet package:</span></span>

    <span data-ttu-id="6ca07-135">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-135">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="6ca07-136">“nuget.org”를 패키지 소스로 선택하고, **찾아보기** 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-136">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="6ca07-137">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-137">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-the-data"></a><span data-ttu-id="6ca07-138">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="6ca07-138">Prepare the data</span></span>

1. <span data-ttu-id="6ca07-139">[iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) 데이터 집합을 다운로드하고 이전 단계에서 만든 *Data* 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-139">Download the [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) data set and save it to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="6ca07-140">아이리스 데이터 집합에 대한 자세한 내용은 [아이리스 꽃 데이터 집합](https://en.wikipedia.org/wiki/Iris_flower_data_set) Wikipedia 페이지와 데이터 집합의 출처인 [아이리스 데이터 집합](http://archive.ics.uci.edu/ml/datasets/Iris) 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ca07-140">For more information about the iris data set, see the [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) Wikipedia page and the [Iris Data Set](http://archive.ics.uci.edu/ml/datasets/Iris) page, which is the source of the data set.</span></span>

1. <span data-ttu-id="6ca07-141">**솔루션 탐색기**에서 *iris.data* 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-141">In **Solution Explorer**, right-click the *iris.data* file and select **Properties**.</span></span> <span data-ttu-id="6ca07-142">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-142">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="6ca07-143">*iris.data* 파일에는 다음을 나타내는 5개의 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-143">The *iris.data* file contains five columns that represent:</span></span>

- <span data-ttu-id="6ca07-144">꽃받침 길이(cm)</span><span class="sxs-lookup"><span data-stu-id="6ca07-144">sepal length in centimetres</span></span>
- <span data-ttu-id="6ca07-145">꽃받침 너비(cm)</span><span class="sxs-lookup"><span data-stu-id="6ca07-145">sepal width in centimetres</span></span>
- <span data-ttu-id="6ca07-146">꽃잎 길이(cm)</span><span class="sxs-lookup"><span data-stu-id="6ca07-146">petal length in centimetres</span></span>
- <span data-ttu-id="6ca07-147">꽃잎 너비(cm)</span><span class="sxs-lookup"><span data-stu-id="6ca07-147">petal width in centimetres</span></span>
- <span data-ttu-id="6ca07-148">아이리스 꽃의 종류</span><span class="sxs-lookup"><span data-stu-id="6ca07-148">type of iris flower</span></span>

<span data-ttu-id="6ca07-149">클러스터링 예제에서 이 자습서는 마지막 열을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-149">For the sake of the clustering example, this tutorial ignores the last column.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="6ca07-150">데이터 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="6ca07-150">Create data classes</span></span>

<span data-ttu-id="6ca07-151">입력 데이터 및 예측에 대한 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-151">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="6ca07-152">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-152">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="6ca07-153">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *IrisData.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-153">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *IrisData.cs*.</span></span> <span data-ttu-id="6ca07-154">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-154">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="6ca07-155">새 파일에 다음 `using` 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-155">Add the following `using` directive to the new file:</span></span>

   [!code-csharp[Add necessary usings](../../../samples/machine-learning/tutorials/IrisClustering/IrisData.cs#1)]

<span data-ttu-id="6ca07-156">기존 클래스 정의를 제거하고 `IrisData` 및 `ClusterPrediction` 클래스를 정의하는 다음 코드를 *IrisData.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-156">Remove the existing class definition and add the following code, which defines the classes `IrisData` and `ClusterPrediction`, to the *IrisData.cs* file:</span></span>

[!code-csharp[Define data classes](../../../samples/machine-learning/tutorials/IrisClustering/IrisData.cs#2)]

<span data-ttu-id="6ca07-157">`IrisData`는 입력 데이터 클래스이며 각 데이터 집합의 각 특징에 대한 정의를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-157">`IrisData` is the input data class and has definitions for each feature from the data set.</span></span> <span data-ttu-id="6ca07-158">[Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) 특성을 사용하여 데이터 집합 파일에서 소스 열의 인덱스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-158">Use the [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) attribute to specify the indices of the source columns in the data set file.</span></span>

<span data-ttu-id="6ca07-159">`ClusterPrediction` 클래스는 `IrisData` 인스턴스에 적용된 클러스터링 모델의 출력을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-159">The `ClusterPrediction` class represents the output of the clustering model applied to an `IrisData` instance.</span></span> <span data-ttu-id="6ca07-160">[ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) 속성을 사용하여 `PredictedClusterId` 및 `Distances` 필드를 각각 **PredictedLabel** 및 **Score** 열에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-160">Use the [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) attribute to bind the `PredictedClusterId` and `Distances` fields to the **PredictedLabel** and **Score** columns respectively.</span></span> <span data-ttu-id="6ca07-161">클러스터링 작업의 경우 이들 열의 의미는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-161">In case of the clustering task those columns has the following meaning:</span></span>

- <span data-ttu-id="6ca07-162">**PredictedLabel**열에는 예측된 클러스터의 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-162">**PredictedLabel** column contains the ID of the predicted cluster.</span></span>
- <span data-ttu-id="6ca07-163">**Score** 열에는 클러스터 중심까지 제곱 유클리드 거리가 있는 배열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-163">**Score** column contains an array with squared Euclidean distances to the cluster centroids.</span></span> <span data-ttu-id="6ca07-164">배열 길이는 클러스터와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-164">The array length is equal to the number of clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="6ca07-165">`float` 유형을 사용하여 입력 및 예측 데이터 클래스에서 부동 소수점 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-165">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="6ca07-166">데이터 및 모델 경로 정의</span><span class="sxs-lookup"><span data-stu-id="6ca07-166">Define data and model paths</span></span>

<span data-ttu-id="6ca07-167">*Program.cs* 파일로 돌아가서 두 개의 필드를 추가하여 데이터 집합 파일에 대한 경로와 모델을 저장할 파일에 대한 경로를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-167">Go back to the *Program.cs* file and add two fields to hold the paths to the data set file and to the file to save the model:</span></span>

- <span data-ttu-id="6ca07-168">`_dataPath`에는 모델을 학습하는 데 사용되는 데이터 집합이 있는 파일에 대한 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-168">`_dataPath` contains the path to the file with the data set used to train the model.</span></span>
- <span data-ttu-id="6ca07-169">`_modelPath`에는 학습된 모델이 저장되는 파일에 대한 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-169">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="6ca07-170">`Main` 메서드 바로 위에 다음 코드를 추가하여 해당 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-170">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Initialize paths](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#1)]

<span data-ttu-id="6ca07-171">위의 코드를 컴파일하려면 *Program.cs* 파일의 맨 위에 있는 다음 `using` 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-171">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add usings for paths](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#2)]

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="6ca07-172">학습 파이프라인 만들기</span><span class="sxs-lookup"><span data-stu-id="6ca07-172">Create a learning pipeline</span></span>

<span data-ttu-id="6ca07-173">*Program.cs* 파일 맨 위에 다음 추가 `using` 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-173">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[Add Microsoft.ML usings](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#3)]

<span data-ttu-id="6ca07-174">`Main` 메서드에서 `Console.WriteLine("Hello World!")`을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-174">In the `Main` method, replace the `Console.WriteLine("Hello World!")` with the following code:</span></span>

[!code-csharp[Call the Train method](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#4)]

<span data-ttu-id="6ca07-175">`Train` 메서드는 모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-175">The `Train` method trains the model.</span></span> <span data-ttu-id="6ca07-176">다음 코드를 사용하여 `Main` 메서드 바로 아래에 해당 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-176">Create that method just below the `Main` method, using the following code:</span></span>

```csharp
private static PredictionModel<IrisData, ClusterPrediction> Train()
{

}
```

<span data-ttu-id="6ca07-177">학습 파이프라인은 모델을 학습시키는 데 필요한 모든 데이터 및 알고리즘을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-177">The learning pipeline loads all of the data and algorithms necessary to train the model.</span></span> <span data-ttu-id="6ca07-178">`Train` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-178">Add the following code into the `Train` method:</span></span>

[!code-csharp[Initialize pipeline](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#5)]

## <a name="load-and-transform-data"></a><span data-ttu-id="6ca07-179">데이터 로드 및 변환</span><span class="sxs-lookup"><span data-stu-id="6ca07-179">Load and transform data</span></span>

<span data-ttu-id="6ca07-180">수행할 첫 번째 단계는 학습 데이터 집합을 로드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-180">The first step to perform is to load the training data set.</span></span> <span data-ttu-id="6ca07-181">이 경우 학습 데이터 집합은 `_dataPath` 필드로 정의된 경로로 텍스트 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-181">In our case, the training data set is stored in the text file with a path defined by the `_dataPath` field.</span></span> <span data-ttu-id="6ca07-182">파일의 열은 쉼표(“,”)로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-182">Columns in the file are separated by the comma (",").</span></span> <span data-ttu-id="6ca07-183">`Train` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-183">Add the following code into the `Train` method:</span></span>

[!code-csharp[Add step to load data](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#6)]

<span data-ttu-id="6ca07-184">다음 단계에서는 <xref:Microsoft.ML.Transforms.ColumnConcatenator> 변환 클래스를 사용하여 모든 기능 열을 **Features** 열에 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-184">The next step is to combine all of the feature columns into the **Features** column using the <xref:Microsoft.ML.Transforms.ColumnConcatenator> transformation class.</span></span> <span data-ttu-id="6ca07-185">기본적으로, 학습 알고리즘은 **Features** 열의 기능만 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-185">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="6ca07-186">다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-186">Add the following code:</span></span>

[!code-csharp[Add step to concatenate columns](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#7)]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="6ca07-187">학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="6ca07-187">Choose a learning algorithm</span></span>

<span data-ttu-id="6ca07-188">파이프라인에 데이터를 추가하고 데이터를 올바른 입력 형식으로 변환한 후 학습 알고리즘(**학습자**)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-188">After adding the data to the pipeline and transforming it into the correct input format, you select a learning algorithm (**learner**).</span></span> <span data-ttu-id="6ca07-189">학습자는 모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-189">The learner trains the model.</span></span> <span data-ttu-id="6ca07-190">ML.NET은 [k-means 알고리즘](https://en.wikipedia.org/wiki/K-means_clustering)을 구현하는 <xref:Microsoft.ML.Trainers.KMeansPlusPlusClusterer> 학습자에게 초기 클러스터 중심을 선택하는 향상된 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-190">ML.NET provides a <xref:Microsoft.ML.Trainers.KMeansPlusPlusClusterer> learner that implements [k-means algorithm](https://en.wikipedia.org/wiki/K-means_clustering) with an improved method for choosing the initial cluster centroids.</span></span>

<span data-ttu-id="6ca07-191">이전 단계에서 추가된 데이터 처리 코드 다음에 오는 `Train` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-191">Add the following code into the `Train` method following the data processing code added in the previous step:</span></span>

[!code-csharp[Add a learner step](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#8)]

<span data-ttu-id="6ca07-192"><xref:Microsoft.ML.Trainers.KMeansPlusPlusClusterer.K?displayProperty=nameWithType> 속성을 사용하여 클러스터 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-192">Use the <xref:Microsoft.ML.Trainers.KMeansPlusPlusClusterer.K?displayProperty=nameWithType> property to specify number of clusters.</span></span> <span data-ttu-id="6ca07-193">위의 코드는 데이터 집합을 3개의 클러스터로 분할해야 함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-193">The code above specifies that the data set should be split in three clusters.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="6ca07-194">모델 학습</span><span class="sxs-lookup"><span data-stu-id="6ca07-194">Train the model</span></span>

<span data-ttu-id="6ca07-195">이전 섹션에서 추가된 단계는 교육을 위한 파이프라인을 준비했지만 아무 것도 실행되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-195">The steps added in the preceding sections prepared the pipeline for training, however, none have been executed.</span></span> <span data-ttu-id="6ca07-196">`pipeline.Train<TInput, TOutput>` 메서드는 `TInput` 형식의 인스턴스를 가져와 `TOutput` 형식의 인스턴스를 출력하는 모델을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-196">The `pipeline.Train<TInput, TOutput>` method produces the model that takes in an instance of the `TInput` type and outputs an instance of the `TOutput` type.</span></span> <span data-ttu-id="6ca07-197">`Train` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-197">Add the following code into the `Train` method:</span></span>

[!code-csharp[Train the model and return](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#9)]

### <a name="save-the-model"></a><span data-ttu-id="6ca07-198">모델 저장</span><span class="sxs-lookup"><span data-stu-id="6ca07-198">Save the model</span></span>

<span data-ttu-id="6ca07-199">이 시점에 기존 또는 새 .NET 응용 프로그램에 통합할 수 있는 모델이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-199">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="6ca07-200">모델을 .zip 파일로 저장하려면 `Train` 메서드 호출 아래의 `Main` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-200">To save your model to a .zip file, add the following code to the `Main` method below the call to the `Train` method:</span></span>

[!code-csharp[Save the model](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#10)]

<span data-ttu-id="6ca07-201">`Main` 메서드에 `await`를 사용하면 `Main` 메서드는 `async` 한정자를 포함하고 `Task`를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-201">Using `await` in the `Main` method means the `Main` method must have the `async` modifier and return a `Task`:</span></span>

[!code-csharp[Make the Main method async](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#11)]

<span data-ttu-id="6ca07-202">또한 *Program.cs* 파일의 맨 위에 있는 다음 `using` 지시문도 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-202">You also need to add the following `using` directive at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add System.Threading.Tasks using](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#12)]

<span data-ttu-id="6ca07-203">`async Main` 메서드는 C# 7.1의 기능이고 프로젝트의 기본 언어 버전은 C# 7.0이므로 언어 버전을 C# 7.1 이상으로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-203">Because the `async Main` method is the feature added in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span> <span data-ttu-id="6ca07-204">이 작업을 하려면 **솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-204">To do that, right-click the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="6ca07-205">**빌드** 탭을 선택하고 **고급** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-205">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="6ca07-206">드롭다운에서 **C# 7.1**(또는 이상 버전)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-206">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="6ca07-207">**확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-207">Select the **OK** button.</span></span>

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="6ca07-208">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="6ca07-208">Use the model for predictions</span></span>

<span data-ttu-id="6ca07-209">테스트 데이터 인스턴스를 수용할 수 있도록 `TestIrisData` 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-209">Create the `TestIrisData` class to house test data instances:</span></span>

1. <span data-ttu-id="6ca07-210">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-210">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="6ca07-211">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *TestIrisData.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-211">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestIrisData.cs*.</span></span> <span data-ttu-id="6ca07-212">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-212">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="6ca07-213">다음 예제처럼 클래스를 static으로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-213">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[Make class static](../../../samples/machine-learning/tutorials/IrisClustering/TestIrisData.cs#1)]

<span data-ttu-id="6ca07-214">이 자습서에서는 이 클래스 내에 하나의 아이리스 데이터 인스턴스를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-214">This tutorial introduces one iris data instance within this class.</span></span> <span data-ttu-id="6ca07-215">이 모델로 실험할 다른 시나리오를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-215">You can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="6ca07-216">다음 코드를 `TestIrisData` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-216">Add the following code into the `TestIrisData` class:</span></span>

[!code-csharp[Test data](../../../samples/machine-learning/tutorials/IrisClustering/TestIrisData.cs#2)]

<span data-ttu-id="6ca07-217">지정된 항목이 속한 클러스터를 찾으려면 *Program.cs* 파일로 돌아가 다음 코드를 `Main` 메서드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-217">To find out the cluster to which the specified item belongs to, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict and output results](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#13)]

<span data-ttu-id="6ca07-218">프로그램을 실행하여 지정된 데이터 인스턴스가 포함된 클러스터와 해당 인스턴스에서 클러스터 중심까지 제곱 거리를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-218">Run the program to see which cluster contains the specified data instance and squared distances from that instance to the cluster centroids.</span></span> <span data-ttu-id="6ca07-219">다음과 같은 결과가 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-219">Your results should be similar to the following.</span></span> <span data-ttu-id="6ca07-220">파이프라인에서 처리되면서 경고 또는 처리 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-220">As the pipeline processes, it might display warnings or processing messages.</span></span> <span data-ttu-id="6ca07-221">이해하기 쉽도록 이러한 결과는 다음 출력에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-221">These have been removed from the following output for clarity.</span></span>

```text
Cluster: 2
Distances: 0.4192338 0.0008847713 0.9660053
```

<span data-ttu-id="6ca07-222">지금까지</span><span class="sxs-lookup"><span data-stu-id="6ca07-222">Congratulations!</span></span> <span data-ttu-id="6ca07-223">이제 아이리스 클러스터링을 위한 기계 학습 모델을 성공적으로 구축하고 예측을 위해 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-223">You've now successfully built a machine learning model for iris clustering and used it to make predictions.</span></span> <span data-ttu-id="6ca07-224">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisClustering) GitHub 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-224">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisClustering) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6ca07-225">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6ca07-225">Next steps</span></span>

<span data-ttu-id="6ca07-226">이 자습서에서는 다음 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca07-226">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="6ca07-227">문제 이해</span><span class="sxs-lookup"><span data-stu-id="6ca07-227">Understand the problem</span></span>
> - <span data-ttu-id="6ca07-228">적절한 기계 학습 작업 선택</span><span class="sxs-lookup"><span data-stu-id="6ca07-228">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="6ca07-229">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="6ca07-229">Prepare the data</span></span>
> - <span data-ttu-id="6ca07-230">데이터 로드 및 변환</span><span class="sxs-lookup"><span data-stu-id="6ca07-230">Load and transform the data</span></span>
> - <span data-ttu-id="6ca07-231">학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="6ca07-231">Choose a learning algorithm</span></span>
> - <span data-ttu-id="6ca07-232">모델 학습</span><span class="sxs-lookup"><span data-stu-id="6ca07-232">Train the model</span></span>
> - <span data-ttu-id="6ca07-233">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="6ca07-233">Use the model for predictions</span></span>

<span data-ttu-id="6ca07-234">학습을 계속하고 더 많은 샘플을 찾으려면 GitHub 리포지토리를 체크 아웃하세요.</span><span class="sxs-lookup"><span data-stu-id="6ca07-234">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="6ca07-235">dotnet/machinelearning GitHub 리포지토리</span><span class="sxs-lookup"><span data-stu-id="6ca07-235">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)
