---
title: 기계 학습 작업
description: ML.NET에서 지원되는 다양한 기계 학습 작업을 살펴봅니다.
ms.date: 06/04/2018
author: aditidugar
ms.author: johalex
ms.openlocfilehash: 22249ac2d275a4168dbd8b03b90d9698fe90f2d1
ms.sourcegitcommit: d8bf4976eafe3289275be3811e7cb721bfff7e1e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34860697"
---
# <a name="machine-learning-tasks"></a><span data-ttu-id="bc40f-103">기계 학습 작업</span><span class="sxs-lookup"><span data-stu-id="bc40f-103">Machine learning tasks</span></span>

<span data-ttu-id="bc40f-104">기계 학습 모델을 빌드할 때 먼저 데이터로 무엇을 달성하려고 하는지 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-104">When building a machine learning model, you first need to define what you are hoping to achieve with your data.</span></span> <span data-ttu-id="bc40f-105">그런 다음, 상황에 맞는 올바른 기계 학습 작업을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-105">After, you can pick the right machine learning task for your situation.</span></span> <span data-ttu-id="bc40f-106">다음 목록은 사용자가 선택할 수 있는 다양한 기계 학습 작업과 몇 가지 일반적인 사용 사례에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-106">The following list describes the different machine learning tasks that you can choose from and some common use cases.</span></span> 

> [!NOTE]
> <span data-ttu-id="bc40f-107">ML.NET은 현재 미리 보기로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-107">ML.NET is currently in Preview.</span></span> <span data-ttu-id="bc40f-108">일부 기계 학습 작업은 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-108">Not all machine learning tasks are currently supported.</span></span> <span data-ttu-id="bc40f-109">특정 작업에 대한 요청을 제출하려면 [dotnet/machinelearning 리포지토리](https://github.com/dotnet/machinelearning/issues)에서 문제를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-109">To submit a request for a certain task, open an issue in the [dotnet/machinelearning repository](https://github.com/dotnet/machinelearning/issues).</span></span>

> [!NOTE]
> <span data-ttu-id="bc40f-110">현재 ML.NET은 이미지가 포함된 기계 학습 작업을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-110">Currently, ML.NET does not support machine learning tasks with images.</span></span> <span data-ttu-id="bc40f-111">향후 릴리스에 지원이 추가될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-111">Support will be added in future releases.</span></span> 

## <a name="binary-classification"></a><span data-ttu-id="bc40f-112">이진 분류</span><span class="sxs-lookup"><span data-stu-id="bc40f-112">Binary classification</span></span>

<span data-ttu-id="bc40f-113">두 클래스(범주) 중에 데이터의 인스턴스가 속한 클래스를 예측하는 데 사용되는 [감독된 기계 학습](glossary.md#supervised-machine-learning) 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-113">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="bc40f-114">분류 알고리즘의 입력은 레이블이 지정된 예제 집합입니다. 여기서 각 레이블은 0 또는 1의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-114">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="bc40f-115">이진 분류 알고리즘의 출력은 분류자로, 레이블이 없는 새 인스턴스의 클래스를 예측하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-115">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="bc40f-116">이진 분류 시나리오의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-116">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="bc40f-117">“긍정적” 또는 “부정적”으로 [Twitter 댓글의 감정 이해](../tutorials/sentiment-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="bc40f-117">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="bc40f-118">환자에게 특정 질병이 있는지 여부 진단.</span><span class="sxs-lookup"><span data-stu-id="bc40f-118">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="bc40f-119">전자 메일을 “스팸”으로 표시할지 여부 결정.</span><span class="sxs-lookup"><span data-stu-id="bc40f-119">Making a decision to mark an email as "spam" or not.</span></span>

## <a name="multi-class-classification"></a><span data-ttu-id="bc40f-120">다중 클래스 분류</span><span class="sxs-lookup"><span data-stu-id="bc40f-120">Multi-class classification</span></span>

<span data-ttu-id="bc40f-121">데이터 인스턴스의 클래스(범주)를 예측하는 데 사용되는 [감독된 기계 학습](glossary.md#supervised-machine-learning) 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-121">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="bc40f-122">분류 알고리즘의 입력은 레이블이 지정된 예제 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-122">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="bc40f-123">각 레이블은 0~k-1 사이의 정수입니다. 여기서 k는 클래스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-123">Each label is an integer between 0 and k-1, where k is the number of classes.</span></span> <span data-ttu-id="bc40f-124">분류 알고리즘의 출력은 분류자로, 레이블이 없는 새 인스턴스의 클래스를 예측하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-124">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="bc40f-125">다중 클래스 분류 시나리오의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-125">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="bc40f-126">개의 품종을 “시베리안 허스키”, “골든 리트리버”, “푸들” 등으로 결정.</span><span class="sxs-lookup"><span data-stu-id="bc40f-126">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="bc40f-127">동영상 리뷰를 “긍정적”, “중립” 또는 “부정적”으로 이해.</span><span class="sxs-lookup"><span data-stu-id="bc40f-127">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="bc40f-128">호텔 리뷰를 “위치”, “가격”, “청결도” 등으로 범주화.</span><span class="sxs-lookup"><span data-stu-id="bc40f-128">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

## <a name="regression"></a><span data-ttu-id="bc40f-129">재발</span><span class="sxs-lookup"><span data-stu-id="bc40f-129">Regression</span></span>

<span data-ttu-id="bc40f-130">관련 기능 집합에서 레이블 값을 예측하는 데 사용되는 [감독된 기계 학습](glossary.md#supervised-machine-learning) 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-130">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="bc40f-131">레이블은 실제 값일 수 있고, 분류 작업과 같이 한정된 값 집합에 속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-131">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="bc40f-132">회귀 알고리즘 모델은 기능 값이 달라질 때 레이블이 변경되는 방식을 결정하기 위한 관련 기능에 대한 레이블의 종속성입니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-132">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="bc40f-133">회귀 알고리즘의 입력은 알려진 값의 레이블이 포함된 예제 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-133">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="bc40f-134">회귀 알고리즘의 출력은 새 입력 기능 집합의 레이블 값을 예측하는 데 사용할 수 있는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-134">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="bc40f-135">회귀 시나리오의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-135">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="bc40f-136">침실 수, 위치 또는 규모와 같은 주택 특성을 기반으로 주택 가격 예측.</span><span class="sxs-lookup"><span data-stu-id="bc40f-136">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="bc40f-137">과거 데이터 및 현재 시장 추세를 기반으로 미래 재고 가격 예측.</span><span class="sxs-lookup"><span data-stu-id="bc40f-137">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="bc40f-138">광고 예산을 기반으로 제품 판매 예측.</span><span class="sxs-lookup"><span data-stu-id="bc40f-138">Predicting sales of a product based on advertising budgets.</span></span>

> [!NOTE]
> <span data-ttu-id="bc40f-139">현재 ML.NET은 시계열이 포함된 회귀 작업에 대한 지원을 빌드하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-139">Currently, ML.NET is still building support for regression tasks that involve time series.</span></span>

## <a name="clustering"></a><span data-ttu-id="bc40f-140">클러스터링</span><span class="sxs-lookup"><span data-stu-id="bc40f-140">Clustering</span></span>

<span data-ttu-id="bc40f-141">데이터 인스턴스를 비슷한 특성을 포함하는 클러스터로 그룹화하는 데 사용되는 [감독되지 않는 기계 학습](glossary.md#unsupervised-machine-learning) 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-141">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="bc40f-142">클러스터링을 사용하여 검색 또는 단순 관찰을 통해 논리적으로 파생될 수 없는 데이터 집합의 관계를 식별할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-142">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="bc40f-143">클러스터링 알고리즘의 입력 및 출력은 선택한 방법에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-143">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="bc40f-144">분산, 중심, 연결 또는 밀도 기반 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-144">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="bc40f-145">현재 ML.NET은 K-평균 클러스터링을 사용하는 중심 기반 방법을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-145">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="bc40f-146">클러스터링 시나리오의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bc40f-146">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="bc40f-147">호텔 선택의 습관과 특성을 기반으로 호텔 투숙객 세그먼트 이해.</span><span class="sxs-lookup"><span data-stu-id="bc40f-147">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="bc40f-148">대상 광고 캠페인을 구축하는 데 도움이 되는 고객 세그먼트 및 인구 통계 식별.</span><span class="sxs-lookup"><span data-stu-id="bc40f-148">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="bc40f-149">제조 메트릭을 기반으로 인벤토리 범주화.</span><span class="sxs-lookup"><span data-stu-id="bc40f-149">Categorizing inventory based on manufacturing metrics.</span></span>

## <a name="anomaly-detection-coming-soon"></a><span data-ttu-id="bc40f-150">변칙 검색(‘출시 예정’)</span><span class="sxs-lookup"><span data-stu-id="bc40f-150">Anomaly detection (*coming soon*)</span></span>

## <a name="ranking-coming-soon"></a><span data-ttu-id="bc40f-151">순위 지정(‘출시 예정’)</span><span class="sxs-lookup"><span data-stu-id="bc40f-151">Ranking (*coming soon*)</span></span>

## <a name="recommendation-coming-soon"></a><span data-ttu-id="bc40f-152">권장 사항(‘출시 예정’)</span><span class="sxs-lookup"><span data-stu-id="bc40f-152">Recommendation (*coming soon*)</span></span>

