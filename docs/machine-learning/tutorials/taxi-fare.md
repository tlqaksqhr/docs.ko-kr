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
# <a name="tutorial-use-mlnet-to-predict-new-york-taxi-fares-regression"></a>자습서: ML.NET을 사용하여 뉴욕 택시 요금 예측(회귀)

> [!NOTE]
> 이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다. 자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.

이 자습서에서는 ML.NET을 사용하여 뉴욕시 택시 요금을 예측하기 위한 [회귀 모델](../resources/glossary.md#regression)을 빌드하는 방법에 대해 설명합니다.

이 자습서에서는 다음 방법을 학습합니다.
> [!div class="checklist"]
> * 문제 이해
> * 적절한 기계 학습 작업 선택
> * 데이터 준비 및 이해
> * 학습 파이프라인 만들기
> * 데이터 로드 및 변환
> * 학습 알고리즘 선택
> * 모델 학습
> * 모델 평가
> * 예측에 모델 사용

## <a name="prerequisites"></a>전제 조건

* “.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 15.6 이상](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).

## <a name="understand-the-problem"></a>문제 이해

이 문제는 **뉴욕시의 택시 요금을 예측**을 중심으로 이루어집니다. 처음에는 요금이 단순히 주행 거리에 따라 결정되는 것처럼 보일 수 있습니다. 그러나 뉴욕 택시 업체는 추가 승객 또는 현금 대신 신용 카드 결제 등의 다른 요소를 고려하여 다양한 금액을 청구합니다.

## <a name="select-the-appropriate-machine-learning-task"></a>적절한 기계 학습 작업 선택

택시 요금을 예측하려면 먼저 적절한 기계 학습 작업을 선택합니다. 데이터 집합의 다른 요소를 기반으로 실제 값(가격을 나타내는 double)을 예측하려고 합니다. [**회귀**](../resources/glossary.md#regression) 작업을 선택합니다.

모델 학습 프로세스는 최종 요금 가격을 예측할 때 가장 영향이 큰 데이터 집합의 요소를 식별합니다.

## <a name="create-a-console-application"></a>콘솔 응용 프로그램 만들기

1. Visual Studio 2017을 엽니다. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다. **새 프로젝트** 대화 상자에서 **Visual C#** 노드와 **.NET Core** 노드를 차례로 선택합니다. 그런 다음 **콘솔 앱(.NET Core)** 프로젝트 템플릿을 선택합니다. **이름** 텍스트 상자에 “TaxiFarePrediction”을 입력하고 **확인** 단추를 선택합니다.

2. 프로젝트에서 *Data* 디렉터리를 만들어 데이터 집합 파일을 저장합니다.

    **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 폴더**를 선택합니다. “Data”를 입력하고 Enter 키를 누릅니다.

3. **Microsoft.ML NuGet 패키지**를 설치합니다.

    솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다. “nuget.org”를 패키지 소스로 선택하고, [찾아보기] 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, **설치** 단추를 선택합니다. **변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.

### <a name="prepare-and-understand-your-data"></a>데이터 준비 및 이해

1. [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) 및 [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) 데이터 집합을 다운로드하여 이전에 만든 *Data* 폴더에 저장합니다. Taxi Trip 데이터 집합은 기계 학습 모델을 학습시키며 모델의 정확도를 평가하는 데 사용될 수 있습니다. 이러한 데이터 집합은 원래 [NYC TLC Taxi Trip 데이터 집합](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)에서 가져옵니다.

2. 솔루션 탐색기에서 각 \*.csv 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다. **고급** 아래에서 **출력 디렉터리에 복사** 값을 **항상**으로 변경합니다.

3. 코드 편집기에서 **taxi-fare-train.csv** 데이터 집합을 열고 첫 번째 행에서 열 머리글을 확인합니다. 각 열을 살펴보세요. 데이터를 이해하고 **기능** 및 **레이블**로 사용할 열을 결정합니다.

**레이블**은 예측하려는 열의 식별자입니다. 식별된 **기능**은 레이블을 예측하는 데 사용됩니다.

* **vendor_id:** 택시 공급업체의 ID가 기능입니다.
* **rate_code:** 택시 이동의 요금 유형이 기능입니다.
* **passenger_count:** 이동하는 승객 수가 기능입니다.
* **trip_time_in_secs**: 이동에 걸린 시간입니다. 이동이 완료된 후까지 걸리는 시간은 모릅니다. 모델에서 이 열을 제외합니다.
* **trip_distance:** 이동 거리가 기능입니다.
* **payment_type:** 결제 방법(현금 또는 신용 카드)이 기능입니다.
* **fare_amount:** 지급한 총 택시 요금이 레이블입니다.

### <a name="create-classes-and-define-paths"></a>클래스 만들기 및 경로 정의

*Program.cs* 파일 맨 위에 다음 추가 `using` 문을 추가합니다.

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

최근에 다운로드한 파일의 경로를 포함하고 모델을 저장할 세 개의 전역 변수를 만들어야 합니다.

* `_datapath`에는 모델을 학습시키는 데 사용되는 데이터 집합의 경로가 포함됩니다.
* `_testdatapath`에는 모델을 평가하는 데 사용되는 데이터 집합의 경로가 포함됩니다.
* `_modelpath`에는 학습된 모델이 저장되는 경로가 포함됩니다.

`Main` 바로 위의 줄에 다음 코드를 추가하여 최근에 다운로드한 파일을 지정합니다.

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

다음으로 입력 데이터 및 예측에 대한 클래스를 만듭니다.

1. **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.
1. **새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *TaxiTrip.cs*로 변경합니다. 그런 다음, **추가** 단추를 선택합니다.
1. 새 파일에 다음 `using` 문을 추가합니다.

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

기존 클래스 정의를 제거하고 두 개의 클래스 `TaxiTrip` 및 `TaxiTripFarePrediction`가 있는 다음 코드를 *TaxiTrip.cs* 파일에 추가합니다.

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

`TaxiTrip`은 입력 데이터 집합 클래스이며 각 데이터 집합 열의 정의를 포함합니다. 모델이 학습된 후에는 `TaxiTripFarePrediction` 클래스가 예측에 사용됩니다. 여기에는 단일 부동(`FareAmount`) 및 `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) 특성이 포함됩니다.

이제 **Program.cs** 파일로 돌아갑니다. `Main`에서 `Console.WriteLine("Hello World!")`를 다음 코드로 바꿉니다.

```csharp
PredictionModel<TaxiTrip, TaxiTripFarePrediction> model = Train();
```

`Train` 메서드는 모델을 학습시킵니다. 다음 코드를 사용하여 `Main` 바로 아래에서만 해당 함수를 만듭니다.

```csharp
public static PredictionModel<TaxiTrip, TaxiTripFarePrediction> Train()
{

}
```

## <a name="create-a-learning-pipeline"></a>학습 파이프라인 만들기

학습 파이프라인은 모델을 학습시키는 데 필요한 모든 데이터 및 알고리즘을 로드합니다. `Train()` 메서드에 다음 코드를 추가합니다.

```csharp
var pipeline = new LearningPipeline();
```

## <a name="load-and-transform-your-data"></a>데이터 로드 및 변환

그런 다음, 데이터를 파이프라인에 로드합니다. 초기에 만들어진 `_datapath`를 가리키고 .csv 파일의 구분 기호(,)를 지정합니다. 마지막 단계 아래의 `Train()` 메서드에 다음 코드를 추가합니다.

```csharp
pipeline.Add(new TextLoader(_datapath).CreateFrom<TaxiTrip>(separator:','));
```

생성 중인 코드에서는 밑줄 없이 열을 참조합니다. `ColumnCopier()` 함수를 사용하여 “레이블”이라는 새 열에 `FareAmount` 열을 복사합니다. 이 열은 **레이블**입니다.

```csharp
pipeline.Add(new ColumnCopier(("FareAmount", "Label")));
```

일부 **기능 엔지니어링**을 수행하여 기계 학습에 효과적으로 사용할 수 있도록 데이터를 변환합니다. 모델을 학습시키는 알고리즘에는 **숫자** 기능이 필요합니다. 범주 데이터(`VendorId`, `RateCode` 및 `PaymentType`)를 숫자로 변환합니다. `CategoricalOneHotVectorizer()` 함수는 이러한 각 열의 값에 숫자 키를 할당합니다. 이 코드를 추가하여 데이터를 변환합니다.

```csharp
pipeline.Add(new CategoricalOneHotVectorizer("VendorId",
                                             "RateCode",
                                             "PaymentType"));
```

데이터 준비의 마지막 단계에서는 `ColumnConcatenator()` 함수를 사용하여 모든 **기능**을 하나의 벡터로 결합합니다. 이 필수 단계를 통해 알고리즘이 기능을 쉽게 처리할 수 있습니다. 다음 코드를 추가합니다.

```csharp
pipeline.Add(new ColumnConcatenator("Features",
                                    "VendorId",
                                    "RateCode",
                                    "PassengerCount",
                                    "TripDistance",
                                    "PaymentType"));
```

`trip_time_in_secs` 열이 포함되지 않은 것을 알 수 있습니다. 이미 유용한 예측 기능이 아니라고 판단했습니다.

> [!NOTE]
> 성공적인 실행을 위해 이러한 단계를 위에 지정된 순서대로 파이프라인에 추가해야 합니다.

## <a name="choose-a-learning-algorithm"></a>학습 알고리즘 선택

파이프라인에 데이터를 추가하고 데이터를 올바른 입력 형식으로 변환한 후 학습 알고리즘(**학습자**)을 선택합니다. 학습 알고리즘은 모델을 학습시킵니다. 이 문제에 대해 **회귀 작업**을 선택했으므로 **그라데이션 승격**을 사용하는 파이프라인에 `FastTreeRegressor()` 학습자를 추가합니다.

그라데이션 승격은 회귀 문제에 대한 기계 학습 기술입니다. 이 파이프라인은 각 회귀 트리를 단계적으로 빌드합니다. 미리 정의된 손실 함수를 사용하여 각 단계에서 오류를 측정한 다음, 수정합니다. 결과는 실제로 더 약한 예측 모델의 앙상블인 예측 모델입니다. 그라데이션 승격에 대한 자세한 내용은 [Boosted Decision Tree Regression](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression)(승격된 의사 결정 트리 회귀)을 참조하세요.

마지막 단계에서 추가된 데이터 처리 코드 다음에 오는 `Train()` 메서드에 다음 코드를 추가합니다.

```csharp
pipeline.Add(new FastTreeRegressor());
```

모든 이전 단계를 개별 문으로 파이프라인에 추가했지만, C#에는 파이프라인을 더 간단하게 만들고 초기화할 수 있는 편리한 컬렉션 초기화 구문이 있습니다. 지금까지 `Train()` 메서드에 추가한 코드를 다음 코드로 바꿉니다.

[!code-csharp[CreatePipeline](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create and initialize the learning pipeline")]

## <a name="train-the-model"></a>모델 학습

마지막 단계에서는 모델을 학습시킵니다. 이 시점까지는 파이프라인에서 아무것도 실행되지 않았습니다. `pipeline.Train<T_Input, T_Output>()` 함수는 미리 정의된 `TaxiTrip` 클래스 형식에서 사용되고 `TaxiTripFarePrediction` 형식을 출력합니다. 이 마지막 코드 조각을 `Train()` 함수에 추가합니다.

[!code-csharp[TrainMOdel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Train your model")]

됐습니다! NYC에서 택시 요금을 예측할 수 있는 기계 학습 모델을 성공적으로 학습시켰습니다. 이제 모델이 얼마나 정확한지 이해하고 모델을 사용하는 방법을 알아보겠습니다.

## <a name="save-the-model"></a>모델 저장

다음 단계로 이동하기 전에 `Train()` 함수의 끝에 다음 코드를 추가하여 모델을 .zip 파일에 저장합니다.

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Save the model asynchronously and return the model")]

`model.WriteAsync()` 호출에 `await` 문을 추가하면 `Train()` 메서드를 `Task`를 반환하는 비동기 메서드로 변경해야 합니다. 다음 코드에 표시된 대로 `Train`의 시그니처를 수정합니다.

[!code-csharp[AsyncTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "Make the Train method async and return a task.")]

`Train` 메서드의 반환 형식을 변경하면 다음 코드에 표시된 대로 `Main` 메서드에서 `Train`을 호출하는 코드에 `await`를 추가해야 합니다.

[!code-csharp[AwaitTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Await the Train method")]

`Main` 메서드에 `await`를 추가하면 `Main` 메서드는 `async` 한정자를 포함하고 `Task`를 반환해야 합니다.

[!code-csharp[AsyncMain](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Make the Main method async and return a task.")]

또한 파일의 맨 위에 있는 문을 사용하여 다음을 추가해야 합니다.

[!code-csharp[UsingTasks](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Add System.Threading.Tasks. to your usings.")]

`async Main` 메서드는 C# 7.1의 새로운 기능이고 프로젝트의 기본 언어 버전은 C# 7.0이므로 언어 버전을 C# 7.1 이상으로 변경해야 합니다.
이 작업을 하려면 **솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다. **빌드** 탭을 선택하고 **고급** 단추를 선택합니다. 드롭다운에서 **C# 7.1**(또는 이상 버전)을 선택합니다. **확인** 단추를 선택합니다.

## <a name="evaluate-the-model"></a>모델 평가

평가는 모델이 얼마나 잘 작동하는지 확인하는 프로세스입니다. 모델은 학습될 때 사용하지 않은 데이터를 기반으로 적절한 예측을 하는 것이 중요합니다. 이를 수행하는 한 가지 방법은 이 자습서에서 한 것처럼 데이터를 학습 및 테스트 데이터 집합으로 분할하는 것입니다. 학습 데이터를 기반으로 모델을 학습시켰으므로 테스트 데이터에서 모델이 얼마나 잘 작동하는지 확인할 수 있습니다.

`Main` 함수로 돌아가서 `Train()` 메서드 호출 아래에 다음 코드를 추가합니다.

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Evaluate the model.")]

`Evaluate()` 함수는 모델을 평가합니다. `Train()` 아래에 해당 함수를 만듭니다. 다음 코드를 추가합니다.

```csharp
private static void Evaluate(PredictionModel<TaxiTrip, TaxiTripFarePrediction> model)
{

}
```

`TextLoader()` 함수를 사용하여 테스트 데이터를 로드합니다. `Evaluate()` 메서드에 다음 코드를 추가합니다.

[!code-csharp[LoadTestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Load the test data.")]

다음 코드를 추가하여 모델을 평가하고 모델에 대한 메트릭을 생성합니다.

[!code-csharp[EvaluateAndMeasure](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Evaluate the model and its predictions.")]

RMS는 회귀 문제를 평가하기 위한 하나의 메트릭입니다. RMS가 낮을수록 모델이 향상됩니다. `Evaluate()` 함수에 다음 코드를 추가하여 모델의 RMS를 인쇄합니다.

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Display the RMS metric.")]

RSquared는 회귀 문제를 평가하기 위한 또 다른 메트릭입니다. RSquared는 0~1 사이의 값입니다. 1에 가까울수록 모델이 향상됩니다. `Evaluate()` 함수에 다음 코드를 추가하여 모델의 RSquared 값을 인쇄합니다.

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Display the RSquared metric.")]

## <a name="use-the-model-for-predictions"></a>예측에 모델 사용

다음으로는 모델이 올바르게 작동하는지 확인하는 데 사용할 수 있는 테스트 시나리오를 수용할 클래스를 만듭니다.

1. **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.
1. **새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *TestTrips.cs*로 변경합니다. 그런 다음, **추가** 단추를 선택합니다.
1. 다음 예제처럼 클래스를 static으로 수정합니다.

[!code-csharp[StaticClass](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#1 "Change class to be a static class.")]

이 자습서에서는 이 클래스 내에서 하나의 테스트 이동을 사용합니다. 나중에 이 샘플로 실험할 다른 시나리오를 추가할 수 있습니다. 다음 코드를 `TestTrips` 클래스에 추가합니다.

[!code-csharp[TestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#2 "Create aq trip to predict its cost.")]

이 이동의 실제 요금은 29.5지만 자리 표시자로 0을 사용합니다. 기계 학습 알고리즘이 요금을 예측합니다.

다음 코드를 `Main` 함수에 추가합니다. `TestTrip` 데이터를 사용하여 모델을 테스트합니다.

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Try a prediction.")]

프로그램을 실행하여 테스트 사례에 대해 예측된 택시 요금을 확인합니다.

지금까지 택시 요금 예측을 위한 기계 학습 모델을 성공적으로 빌드하고, 정확도를 평가하고, 모델을 테스트했습니다. [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 다음 방법을 학습했습니다.
> [!div class="checklist"]
> * 문제 이해
> * 적절한 기계 학습 작업 선택
> * 데이터 준비 및 이해
> * 학습 파이프라인 만들기
> * 데이터 로드 및 변환
> * 학습 알고리즘 선택
> * 모델 학습
> * 모델 평가
> * 예측에 모델 사용

학습을 계속하고 더 많은 샘플을 찾으려면 GitHub 리포지토리를 체크 아웃하세요.
> [!div class="nextstepaction"]
> [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/)
