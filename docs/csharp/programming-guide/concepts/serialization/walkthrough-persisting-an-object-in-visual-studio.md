---
title: '연습: C#을 사용하여 개체 유지'
ms.date: 04/26/2018
ms.openlocfilehash: 6c9719dc3aaf997ea144515a553f787450e54041
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
---
# <a name="walkthrough-persisting-an-object-using-c"></a><span data-ttu-id="a126d-102">연습: C#을 사용하여 개체 유지</span><span class="sxs-lookup"><span data-stu-id="a126d-102">Walkthrough: persisting an object using C#</span></span> #

<span data-ttu-id="a126d-103">serialization을 사용하면 인스턴스 간에 개체의 데이터를 유지할 수 있으므로, 다음에 개체를 인스턴스화할 때 값을 저장하고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-103">You can use serialization to persist an object's data between instances, which enables you to store values and retrieve them the next time that the object is instantiated.</span></span>

<span data-ttu-id="a126d-104">이 연습에서는 기본 `Loan` 개체를 만들고 데이터를 파일에 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-104">In this walkthrough, you will create a basic `Loan` object and persist its data to a file.</span></span> <span data-ttu-id="a126d-105">그런 다음 개체를 다시 만들 때 파일에서 데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-105">You will then retrieve the data from the file when you re-create the object.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a126d-106">이 예제에서는 파일이 아직 없는 경우 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-106">This example creates a new file if the file does not already exist.</span></span> <span data-ttu-id="a126d-107">응용 프로그램에서 파일을 만들어야 하는 경우 해당 응용 프로그램은 폴더에 대한 `Create` 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-107">If an application must create a file, that application must have `Create` permission for the folder.</span></span> <span data-ttu-id="a126d-108">권한은 액세스 제어 목록을 사용하여 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-108">Permissions are set by using access control lists.</span></span> <span data-ttu-id="a126d-109">파일이 이미 있는 경우, 응용 프로그램에는 더 낮은 권한인 `Write` 권한만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-109">If the file already exists, the application needs only `Write` permission, a lesser permission.</span></span> <span data-ttu-id="a126d-110">가능한 경우 배포하는 동안 파일을 만드는 것이 안전하며, 폴더에 대한 Create 권한 대신 단일 파일에 대해 `Read` 권한만 부여하는 것이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-110">Where possible, it's more secure to create the file during deployment and only grant `Read` permissions to a single file (instead of Create permissions for a folder).</span></span> <span data-ttu-id="a126d-111">또한 루트 폴더나 Program Files 폴더보다 사용자 폴더에 데이터를 쓰는 것이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-111">Also, it's more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a126d-112">이 예제에서는 이진 형식 파일의 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-112">This example stores data in a binary format file.</span></span> <span data-ttu-id="a126d-113">이러한 형식은 암호 또는 신용 카드 정보와 같은 중요한 데이터에 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-113">These formats should not be used for sensitive data, such as passwords or credit-card information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a126d-114">전제 조건</span><span class="sxs-lookup"><span data-stu-id="a126d-114">Prerequisites</span></span>

* <span data-ttu-id="a126d-115">빌드하고 실행하려면 [.NET Core SDK](https://www.microsoft.com/net/core)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-115">To build and run, install the [.NET Core SDK](https://www.microsoft.com/net/core).</span></span>

* <span data-ttu-id="a126d-116">아직 없는 경우 즐겨 찾는 코드 편집기를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-116">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="a126d-117">코드 편집기를 설치해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="a126d-117">Need to install a code editor?</span></span> <span data-ttu-id="a126d-118">[Visual Studio](https://visualstudio.com/downloads)를 체험해 보세요.</span><span class="sxs-lookup"><span data-stu-id="a126d-118">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

<span data-ttu-id="a126d-119">[.NET 샘플 GitHub 리포지토리에서](https://github.com/dotnet/samples/tree/master/csharp/serialization) 온라인으로 샘플 코드를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-119">You can examine the sample code online [at the .NET samples GitHub repository](https://github.com/dotnet/samples/tree/master/csharp/serialization).</span></span>

## <a name="creating-the-loan-object"></a><span data-ttu-id="a126d-120">Loan 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="a126d-120">Creating the loan object</span></span>

<span data-ttu-id="a126d-121">첫 번째 단계는 `Loan` 클래스와 이 클래스를 사용하는 콘솔 응용 프로그램을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-121">The first step is to create a `Loan` class and a console application that uses the class:</span></span>

1. <span data-ttu-id="a126d-122">새 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-122">Create a new application.</span></span> <span data-ttu-id="a126d-123">`dotnet new console -o serialization`을 입력하여 `serialization`이라는 하위 디렉터리에서 새 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-123">Type `dotnet new console -o serialization` to create a new console application in a subdirectory named `serialization`.</span></span>
1. <span data-ttu-id="a126d-124">편집기에서 응용 프로그램을 열고 `Loan.cs`라는 새 클래스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-124">Open the application in your editor, and add a new class named `Loan.cs`.</span></span>
1. <span data-ttu-id="a126d-125">`Loan` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-125">Add the following code to your `Loan` class:</span></span>

[!code-csharp[Loan class definition](../../../../../samples/csharp/serialization/Loan.cs#1)]

<span data-ttu-id="a126d-126">`Loan` 클래스를 사용하는 응용 프로그램도 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-126">You will also have to create an application that uses the `Loan` class.</span></span>

## <a name="serialize-the-loan-object"></a><span data-ttu-id="a126d-127">Loan 개체 직렬화</span><span class="sxs-lookup"><span data-stu-id="a126d-127">Serialize the loan object</span></span>

1. <span data-ttu-id="a126d-128">`Program.cs`를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-128">Open `Program.cs`.</span></span> <span data-ttu-id="a126d-129">다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-129">Add the following code:</span></span>

[!code-csharp[Create a loan object](../../../../../samples/csharp/serialization/Program.cs#1)]

<span data-ttu-id="a126d-130">`PropertyChanged` 이벤트에 대한 이벤트 처리기를 추가하고 `Loan` 개체를 수정하고 변경 내용을 표시하는 몇 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-130">Add an event handler for the `PropertyChanged` event, and a few lines to modify the `Loan` object and display the changes.</span></span> <span data-ttu-id="a126d-131">다음 코드에서 추가된 기능을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-131">You can see the additions in the following code:</span></span>

[!code-csharp[Listening for the PropertyChanged event](../../../../../samples/csharp/serialization/Program.cs#2)]

<span data-ttu-id="a126d-132">이 시점에서 코드를 실행하고 현재 출력을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-132">At this point, you can run the code, and see the current output:</span></span>

```console
New customer value: Henry Clay
7.5
7.1
```

<span data-ttu-id="a126d-133">이 응용 프로그램을 반복해서 실행하면 항상 동일한 값을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-133">Running this application repeatedly always writes the same values.</span></span> <span data-ttu-id="a126d-134">프로그램을 실행할 때마다 새로운 Loan 개체가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-134">A new Loan object is created every time you run the program.</span></span> <span data-ttu-id="a126d-135">현실 세계에서 금리는 주기적으로 변경되지만, 애플리케이션이 실행될 때마다 변경되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-135">In the real world, interest rates change periodically, but not necessarily every time that the application is run.</span></span> <span data-ttu-id="a126d-136">Serialization 코드는 응용 프로그램의 인스턴스 간에 가장 최근 이자율을 유지함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-136">Serialization code means you preserve the most recent interest rate between instances of the application.</span></span> <span data-ttu-id="a126d-137">다음 단계에서는 Loan 클래스에 serialization을 추가하여 이를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-137">In the next step, you will do just that by adding serialization to the Loan class.</span></span>

## <a name="using-serialization-to-persist-the-object"></a><span data-ttu-id="a126d-138">Serialization을 사용하여 개체 유지</span><span class="sxs-lookup"><span data-stu-id="a126d-138">Using Serialization to Persist the Object</span></span>

<span data-ttu-id="a126d-139">Loan 클래스의 값을 유지하려면 먼저 클래스를 `Serializable` 속성으로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-139">In order to persist the values for the Loan class, you must first mark the class with the `Serializable` attribute.</span></span> <span data-ttu-id="a126d-140">Loan 클래스 선언 위에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-140">Add the following code above the Loan class definition:</span></span>

[!code-csharp[Loan class definition](../../../../../samples/csharp/serialization/Loan.cs#2)]

<span data-ttu-id="a126d-141"><xref:System.SerializableAttribute>는 클래스의 모든 내용을 파일에 유지할 수 있음을 컴파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-141">The <xref:System.SerializableAttribute> tells the compiler that everything in the class can be persisted to a file.</span></span> <span data-ttu-id="a126d-142">`PropertyChanged` 이벤트가 저장되어야 하는 개체 그래프의 일부를 나타내지 않기 때문에 직렬화되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-142">Because the `PropertyChanged` event does not represent part of the object graph that should be stored, it should not be serialized.</span></span> <span data-ttu-id="a126d-143">그러면 해당 이벤트에 연결된 모든 개체를 직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-143">Doing so would serialize all objects that are attached to that event.</span></span> <span data-ttu-id="a126d-144">`PropertyChanged` 이벤트 처리기의 필드 선언에 <xref:System.NonSerializedAttribute>를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-144">You can add the <xref:System.NonSerializedAttribute> to the field declaration for the `PropertyChanged` event handler.</span></span>

[!code-csharp[Disable serialization for the event handler](../../../../../samples/csharp/serialization/Loan.cs#3)]

<span data-ttu-id="a126d-145">C# 7.3부터는 `field` 대상 값을 사용하여 자동 구현 속성의 지원 필드에 특성을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-145">Beginning with C# 7.3, you can attach attributes to the backing field of an auto-implemented property using the `field` target value.</span></span> <span data-ttu-id="a126d-146">다음 코드에서는 `TimeLastLoaded` 속성을 추가하고 직렬화할 수 없음으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-146">The following code adds a `TimeLastLoaded` property and marks it as not serializable:</span></span>

[!code-csharp[Disable serialization for an auto-implemented property](../../../../../samples/csharp/serialization/Loan.cs#4)]

<span data-ttu-id="a126d-147">다음 단계는 LoanApp 응용 프로그램에 serialization 코드를 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-147">The next step is to add the serialization code to the LoanApp application.</span></span> <span data-ttu-id="a126d-148">클래스를 serialize하여 파일에 쓰려면 <xref:System.IO> 및 <xref:System.Runtime.Serialization.Formatters.Binary> 네임스페이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-148">In order to serialize the class and write it to a file, you use the <xref:System.IO> and <xref:System.Runtime.Serialization.Formatters.Binary> namespaces.</span></span> <span data-ttu-id="a126d-149">정규화된 이름을 입력하지 않으려면 필요한 다음 코드에 표시된 대로 필요한 네임스페이스에 참조를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-149">To avoid typing the fully qualified names, you can add references to the necessary namespaces as shown in the following code:</span></span>

[!code-csharp[Adding namespaces for serialization](../../../../../samples/csharp/serialization/Program.cs#3)]

<span data-ttu-id="a126d-150">다음 단계는 개체를 만들 때 파일에서 개체를 deserialize할 코드를 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-150">The next step is to add code to deserialize the object from the file when the object is created.</span></span> <span data-ttu-id="a126d-151">다음 코드에 표시된 대로 직렬화된 데이터의 파일 이름에 대한 클래스에 상수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-151">Add a constant to the class for the serialized data's file name as shown in the following code:</span></span>

[!code-csharp[Define the name of the saved file](../../../../../samples/csharp/serialization/Program.cs#4)]

<span data-ttu-id="a126d-152">다음으로 `TestLoan` 개체를 만든 줄 뒤에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-152">Next, add the following code after the line that creates the `TestLoan` object:</span></span>

[!code-csharp[Read from a file if it exists](../../../../../samples/csharp/serialization/Program.cs#5)]

<span data-ttu-id="a126d-153">먼저 파일이 있는지를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-153">You first must check that the file exists.</span></span> <span data-ttu-id="a126d-154">파일이 있으면 이진 파일을 읽는 <xref:System.IO.Stream> 클래스와 파일을 변환하는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-154">If it exists, create a <xref:System.IO.Stream> class to read the binary file and a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> class to translate the file.</span></span> <span data-ttu-id="a126d-155">또한 스트림 형식에서 Loan 개체 형식으로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-155">You also need to convert from the stream type to the Loan object type.</span></span>

<span data-ttu-id="a126d-156">다음으로 클래스를 직렬화하는 코드를 파일에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-156">Next you must add code to serialize the class to a file.</span></span> <span data-ttu-id="a126d-157">`Main` 메서드에서 기존 코드 뒤에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-157">Add the following code after the existing code in the `Main` method:</span></span>

[!code-csharp[Save the existing Loan object](../../../../../samples/csharp/serialization/Program.cs#6)]

<span data-ttu-id="a126d-158">이 시점에서 다시 응용 프로그램을 빌드 및 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-158">At this point, you can again build and run the application.</span></span> <span data-ttu-id="a126d-159">처음으로 실행되면 이자율이 7.5에서 시작한 다음, 7.1로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-159">The first time it runs, notice that the interest rates starts at 7.5, and then changes to 7.1.</span></span> <span data-ttu-id="a126d-160">응용 프로그램을 닫았다가 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-160">Close the application and then run it again.</span></span> <span data-ttu-id="a126d-161">이제 응용 프로그램이 저장된 파일을 읽는 메시지를 인쇄하고 이자율은 코드가 변경하기 전에도 7.1입니다.</span><span class="sxs-lookup"><span data-stu-id="a126d-161">Now, the application prints the message that it has read the saved file, and the interest rate is 7.1 even before the code that changes it.</span></span>

## <a name="see-also"></a><span data-ttu-id="a126d-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a126d-162">See also</span></span>

 [<span data-ttu-id="a126d-163">serialization(C#)</span><span class="sxs-lookup"><span data-stu-id="a126d-163">Serialization (C# )</span></span>](index.md)  
 [<span data-ttu-id="a126d-164">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a126d-164">C# Programming Guide</span></span>](../..//index.md)  
