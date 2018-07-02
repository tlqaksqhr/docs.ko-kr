---
title: 기계 학습 작업
description: ML.NET에서 지원되는 다양한 기계 학습 작업을 살펴봅니다.
ms.date: 06/04/2018
author: aditidugar
ms.author: johalex
ms.openlocfilehash: 875006a9cddb87b5f9436b78773420858fd842dd
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207728"
---
# <a name="machine-learning-tasks"></a><span data-ttu-id="cebfb-103">기계 학습 작업</span><span class="sxs-lookup"><span data-stu-id="cebfb-103">Machine learning tasks</span></span>

<span data-ttu-id="cebfb-104">기계 학습 모델을 빌드할 때 먼저 데이터로 무엇을 달성하려고 하는지 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-104">When building a machine learning model, you first need to define what you are hoping to achieve with your data.</span></span> <span data-ttu-id="cebfb-105">그런 다음, 상황에 맞는 올바른 기계 학습 작업을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-105">After, you can pick the right machine learning task for your situation.</span></span> <span data-ttu-id="cebfb-106">다음 목록은 사용자가 선택할 수 있는 다양한 기계 학습 작업과 몇 가지 일반적인 사용 사례에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-106">The following list describes the different machine learning tasks that you can choose from and some common use cases.</span></span> 

> [!NOTE]
> <span data-ttu-id="cebfb-107">ML.NET은 현재 미리 보기로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-107">ML.NET is currently in Preview.</span></span> <span data-ttu-id="cebfb-108">일부 기계 학습 작업은 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-108">Not all machine learning tasks are currently supported.</span></span> <span data-ttu-id="cebfb-109">특정 작업에 대한 요청을 제출하려면 [dotnet/machinelearning 리포지토리](https://github.com/dotnet/machinelearning/issues)에서 문제를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-109">To submit a request for a certain task, open an issue in the [dotnet/machinelearning repository](https://github.com/dotnet/machinelearning/issues).</span></span>

> [!NOTE]
> <span data-ttu-id="cebfb-110">현재 ML.NET은 이미지가 포함된 기계 학습 작업을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-110">Currently, ML.NET does not support machine learning tasks with images.</span></span> <span data-ttu-id="cebfb-111">향후 릴리스에 지원이 추가될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-111">Support will be added in future releases.</span></span> 

## <a name="binary-classification"></a><span data-ttu-id="cebfb-112">이진 분류</span><span class="sxs-lookup"><span data-stu-id="cebfb-112">Binary classification</span></span>

<span data-ttu-id="cebfb-113">두 클래스(범주) 중에 데이터의 인스턴스가 속한 클래스를 예측하는 데 사용되는 [감독된 기계 학습](glossary.md#supervised-machine-learning) 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-113">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="cebfb-114">분류 알고리즘의 입력은 레이블이 지정된 예제 집합입니다. 여기서 각 레이블은 0 또는 1의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-114">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="cebfb-115">이진 분류 알고리즘의 출력은 분류자로, 레이블이 없는 새 인스턴스의 클래스를 예측하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-115">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="cebfb-116">이진 분류 시나리오의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-116">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="cebfb-117">“긍정적” 또는 “부정적”으로 [Twitter 댓글의 감정 이해](../tutorials/sentiment-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="cebfb-117">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="cebfb-118">환자에게 특정 질병이 있는지 여부 진단.</span><span class="sxs-lookup"><span data-stu-id="cebfb-118">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="cebfb-119">전자 메일을 “스팸”으로 표시할지 여부 결정.</span><span class="sxs-lookup"><span data-stu-id="cebfb-119">Making a decision to mark an email as "spam" or not.</span></span>

<span data-ttu-id="cebfb-120">자세한 내용은 Wikipedia에서 [Binary classification](https://en.wikipedia.org/wiki/Binary_classification)(이진 분류) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cebfb-120">For more information, see the [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) article on Wikipedia.</span></span>

## <a name="multiclass-classification"></a><span data-ttu-id="cebfb-121">다중 클래스 분류</span><span class="sxs-lookup"><span data-stu-id="cebfb-121">Multiclass classification</span></span>

<span data-ttu-id="cebfb-122">데이터 인스턴스의 클래스(범주)를 예측하는 데 사용되는 [감독된 기계 학습](glossary.md#supervised-machine-learning) 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-122">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="cebfb-123">분류 알고리즘의 입력은 레이블이 지정된 예제 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-123">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="cebfb-124">각 레이블은 0~k-1 사이의 정수입니다. 여기서 k는 클래스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-124">Each label is an integer between 0 and k-1, where k is the number of classes.</span></span> <span data-ttu-id="cebfb-125">분류 알고리즘의 출력은 분류자로, 레이블이 없는 새 인스턴스의 클래스를 예측하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-125">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="cebfb-126">다중 클래스 분류 시나리오의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-126">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="cebfb-127">개의 품종을 “시베리안 허스키”, “골든 리트리버”, “푸들” 등으로 결정.</span><span class="sxs-lookup"><span data-stu-id="cebfb-127">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="cebfb-128">동영상 리뷰를 “긍정적”, “중립” 또는 “부정적”으로 이해.</span><span class="sxs-lookup"><span data-stu-id="cebfb-128">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="cebfb-129">호텔 리뷰를 “위치”, “가격”, “청결도” 등으로 범주화.</span><span class="sxs-lookup"><span data-stu-id="cebfb-129">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

<span data-ttu-id="cebfb-130">자세한 내용은 Wikipedia에서 [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification)(다중 클래스 분류) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cebfb-130">For more information, see the [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) article on Wikipedia.</span></span>

## <a name="regression"></a><span data-ttu-id="cebfb-131">재발</span><span class="sxs-lookup"><span data-stu-id="cebfb-131">Regression</span></span>

<span data-ttu-id="cebfb-132">관련 기능 집합에서 레이블 값을 예측하는 데 사용되는 [감독된 기계 학습](glossary.md#supervised-machine-learning) 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-132">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="cebfb-133">레이블은 실제 값일 수 있고, 분류 작업과 같이 한정된 값 집합에 속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-133">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="cebfb-134">회귀 알고리즘 모델은 기능 값이 달라질 때 레이블이 변경되는 방식을 결정하기 위한 관련 기능에 대한 레이블의 종속성입니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-134">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="cebfb-135">회귀 알고리즘의 입력은 알려진 값의 레이블이 포함된 예제 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-135">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="cebfb-136">회귀 알고리즘의 출력은 새 입력 기능 집합의 레이블 값을 예측하는 데 사용할 수 있는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-136">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="cebfb-137">회귀 시나리오의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-137">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="cebfb-138">침실 수, 위치 또는 규모와 같은 주택 특성을 기반으로 주택 가격 예측.</span><span class="sxs-lookup"><span data-stu-id="cebfb-138">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="cebfb-139">과거 데이터 및 현재 시장 추세를 기반으로 미래 재고 가격 예측.</span><span class="sxs-lookup"><span data-stu-id="cebfb-139">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="cebfb-140">광고 예산을 기반으로 제품 판매 예측.</span><span class="sxs-lookup"><span data-stu-id="cebfb-140">Predicting sales of a product based on advertising budgets.</span></span>

> [!NOTE]
> <span data-ttu-id="cebfb-141">현재 ML.NET은 시계열이 포함된 회귀 작업에 대한 지원을 빌드하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-141">Currently, ML.NET is still building support for regression tasks that involve time series.</span></span>

## <a name="clustering"></a><span data-ttu-id="cebfb-142">클러스터링</span><span class="sxs-lookup"><span data-stu-id="cebfb-142">Clustering</span></span>

<span data-ttu-id="cebfb-143">데이터 인스턴스를 비슷한 특성을 포함하는 클러스터로 그룹화하는 데 사용되는 [감독되지 않는 기계 학습](glossary.md#unsupervised-machine-learning) 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-143">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="cebfb-144">클러스터링을 사용하여 검색 또는 단순 관찰을 통해 논리적으로 파생될 수 없는 데이터 집합의 관계를 식별할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-144">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="cebfb-145">클러스터링 알고리즘의 입력 및 출력은 선택한 방법에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-145">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="cebfb-146">분산, 중심, 연결 또는 밀도 기반 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-146">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="cebfb-147">현재 ML.NET은 K-평균 클러스터링을 사용하는 중심 기반 방법을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-147">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="cebfb-148">클러스터링 시나리오의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cebfb-148">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="cebfb-149">호텔 선택의 습관과 특성을 기반으로 호텔 투숙객 세그먼트 이해.</span><span class="sxs-lookup"><span data-stu-id="cebfb-149">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="cebfb-150">대상 광고 캠페인을 구축하는 데 도움이 되는 고객 세그먼트 및 인구 통계 식별.</span><span class="sxs-lookup"><span data-stu-id="cebfb-150">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="cebfb-151">제조 메트릭을 기반으로 인벤토리 범주화.</span><span class="sxs-lookup"><span data-stu-id="cebfb-151">Categorizing inventory based on manufacturing metrics.</span></span>

## <a name="anomaly-detection-coming-soon"></a><span data-ttu-id="cebfb-152">변칙 검색(‘출시 예정’)</span><span class="sxs-lookup"><span data-stu-id="cebfb-152">Anomaly detection (*coming soon*)</span></span>

## <a name="ranking-coming-soon"></a><span data-ttu-id="cebfb-153">순위 지정(‘출시 예정’)</span><span class="sxs-lookup"><span data-stu-id="cebfb-153">Ranking (*coming soon*)</span></span>

## <a name="recommendation-coming-soon"></a><span data-ttu-id="cebfb-154">권장 사항(‘출시 예정’)</span><span class="sxs-lookup"><span data-stu-id="cebfb-154">Recommendation (*coming soon*)</span></span>

