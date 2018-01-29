---
title: ".NET Core에서 Microsoft XML Serializer Generator 사용"
description: "Microsoft XML Serializer Generator에 대한 개요입니다."
author: mlacouture
manager: wpickett
ms.author: johalex
ms.date: 01/19/2017
ms.topic: tutorial
ms.prod: .net-core
ms.custom: mvc
ms.openlocfilehash: b2f52a068d128b2eb978c9e086508bd87e103ebc
ms.sourcegitcommit: dd6ea7f0e581ac84e0a90d9b23c463fcf1ec3ce7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2018
---
# <a name="using-microsoft-xml-serializer-generator-on-net-core"></a><span data-ttu-id="b1737-103">.NET Core에서 Microsoft XML Serializer Generator 사용</span><span class="sxs-lookup"><span data-stu-id="b1737-103">Using Microsoft XML Serializer Generator on .NET Core</span></span>

<span data-ttu-id="b1737-104">이 자습서에서는 C# .NET Core 응용 프로그램에서 Microsoft XML Serializer Generator를 사용하는 방법을 배웁니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-104">This tutorial teaches you how to use the Microsoft XML Serializer Generator in a C# .NET Core application.</span></span> <span data-ttu-id="b1737-105">이 자습서를 진행하면서 다음을 익히게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-105">During the course of this tutorial, you learn:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="b1737-106">.NET Core 앱을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="b1737-106">How to create a .NET Core app</span></span>
> * <span data-ttu-id="b1737-107">Microsoft.XmlSerializer.Generator 패키지에 대한 참조를 추가하는 방법</span><span class="sxs-lookup"><span data-stu-id="b1737-107">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> * <span data-ttu-id="b1737-108">MyApp.csproj를 편집하여 종속성을 추가하는 방법</span><span class="sxs-lookup"><span data-stu-id="b1737-108">How to edit your MyApp.csproj to add dependencies</span></span>
> * <span data-ttu-id="b1737-109">클래스 및 XmlSerializer를 추가하는 방법</span><span class="sxs-lookup"><span data-stu-id="b1737-109">How to add a class and an XmlSerializer</span></span>
> * <span data-ttu-id="b1737-110">응용 프로그램을 빌드하고 실행하는 방법</span><span class="sxs-lookup"><span data-stu-id="b1737-110">How to build and run the application</span></span> 

<span data-ttu-id="b1737-111">.NET Framework용 [Xml Serializer Generator(sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md)와 마찬가지로, [Microsoft.XmlSerializer.Generator NuGet 패키지](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator)는 .NET Core 및 .NET Standard 프로젝트와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-111">Like the [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) for the .NET Framework, the [Microsoft.XmlSerializer.Generator NuGet package](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) is the equivalent for .NET Core and .NET Standard projects.</span></span> <span data-ttu-id="b1737-112"><xref:System.Xml.Serialization.XmlSerializer>를 사용하여 해당 형식의 개체를 직렬화하거나 역직렬화할 때 XML serialization의 시작 성능을 향상시키기 위해 어셈블리에 포함된 형식의 XML serialization 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-112">It creates an XML serialization assembly for types contained in an assembly to improve the startup performance of XML serialization when serializing or de-serializing objects of those types using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b1737-113">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="b1737-113">Prerequisites</span></span>

<span data-ttu-id="b1737-114">이 자습서를 완료하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-114">To complete this tutorial:</span></span>

* <span data-ttu-id="b1737-115">[.NET Core SDK 2.1.3 이상](https://www.microsoft.com/net/download) 설치</span><span class="sxs-lookup"><span data-stu-id="b1737-115">Install [.NET Core SDK 2.1.3 or later](https://www.microsoft.com/net/download)</span></span>
* <span data-ttu-id="b1737-116">아직 없는 경우 즐겨 찾는 코드 편집기를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-116">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="b1737-117">코드 편집기를 설치해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="b1737-117">Need to install a code editor?</span></span> <span data-ttu-id="b1737-118">[Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)를 체험해 보세요.</span><span class="sxs-lookup"><span data-stu-id="b1737-118">Try [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)!</span></span>
  
## <a name="use-microsoft-xml-serializer-generator-in-a-net-core-console-application"></a><span data-ttu-id="b1737-119">.NET Core 콘솔 응용 프로그램에서 Microsoft XML Serializer Generator 사용</span><span class="sxs-lookup"><span data-stu-id="b1737-119">Use Microsoft XML Serializer Generator in a .NET Core console application</span></span> 

<span data-ttu-id="b1737-120">다음 지침은 .NET Core 콘솔 응용 프로그램에서 Microsoft XML Serializer Generator를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-120">The following instructions show you how to use XML Serializer Generator in a .NET Core console application.</span></span>

### <a name="create-a-net-core-console-application"></a><span data-ttu-id="b1737-121">.NET Core 콘솔 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="b1737-121">Create a .NET Core console application</span></span>

<span data-ttu-id="b1737-122">명령 프롬프트를 열고 *MyApp*이라는 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-122">Open a command prompt and create a folder named *MyApp*.</span></span> <span data-ttu-id="b1737-123">만든 폴더로 이동하고 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-123">Navigate to the folder you created and type the following command:</span></span>

```console
dotnet new console
```

### <a name="add-a-reference-to-the-microsoftxmlserializergenerator-package-in-the-myapp-project"></a><span data-ttu-id="b1737-124">MyApp 프로젝트에서 Microsoft.XmlSerializer.Generator 패키지에 대한 참조 추가</span><span class="sxs-lookup"><span data-stu-id="b1737-124">Add a reference to the Microsoft.XmlSerializer.Generator package in the MyApp project</span></span>

<span data-ttu-id="b1737-125">[`dotnet add package`](../tools//dotnet-add-package.md) 명령을 사용하여 프로젝트에 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-125">Use the [`dotnet add package`](../tools//dotnet-add-package.md) command to add the reference in your project.</span></span> 

<span data-ttu-id="b1737-126">유형:</span><span class="sxs-lookup"><span data-stu-id="b1737-126">Type:</span></span>
 
 ```console
 dotnet add package Microsoft.XmlSerializer.Generator -v 1.0.0
 ```
 
### <a name="verify-changes-to-myappcsproj-after-adding-the-package"></a><span data-ttu-id="b1737-127">패키지를 추가한 후 MyApp.csproj 변경 사항 확인</span><span class="sxs-lookup"><span data-stu-id="b1737-127">Verify changes to MyApp.csproj after adding the package</span></span>

<span data-ttu-id="b1737-128">코드 편집기를 열고 시작해 보겠습니다!</span><span class="sxs-lookup"><span data-stu-id="b1737-128">Open your code editor and let's get started!</span></span> <span data-ttu-id="b1737-129">앱을 빌드한 *MyApp* 디렉터리에서 계속 작업 중입니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-129">We're still working from the *MyApp* directory we built the app in.</span></span>

<span data-ttu-id="b1737-130">텍스트 편집기에서 *MyApp.csproj*를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-130">Open *MyApp.csproj* in your text editor.</span></span>

<span data-ttu-id="b1737-131">[`dotnet add package`](../tools//dotnet-add-package.md) 명령을 실행하면 다음 줄이 *MyApp.csproj* 프로젝트 파일에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-131">After running the [`dotnet add package`](../tools//dotnet-add-package.md) command, the following lines are added to your *MyApp.csproj* project file:</span></span>

 ```xml
 <ItemGroup>
    <PackageReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```
 
### <a name="add-another-itemgroup-section-for-net-core-cli-tool-support"></a><span data-ttu-id="b1737-132">.NET Core CLI 도구 지원을 위해 다른 ItemGroup 섹션 추가</span><span class="sxs-lookup"><span data-stu-id="b1737-132">Add another ItemGroup section for .NET Core CLI Tool support</span></span>
 
 <span data-ttu-id="b1737-133">검사한 `ItemGroup` 섹션 뒤에 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-133">Add the following lines after the `ItemGroup` section that we inspected:</span></span>
 
 ```xml
 <ItemGroup>
    <DotNetCliToolReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```
 
### <a name="add-a-class-in-the-application"></a><span data-ttu-id="b1737-134">응용 프로그램에서 클래스 추가</span><span class="sxs-lookup"><span data-stu-id="b1737-134">Add a class in the application</span></span>

<span data-ttu-id="b1737-135">텍스트 편집기에서 *Program.cs*를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-135">Open *Program.cs* in your text editor.</span></span> <span data-ttu-id="b1737-136">*Program.cs*에서 *MyClass*라는 클래스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-136">Add the class named *MyClass* in *Program.cs*.</span></span>

```csharp
public class MyClass
{
   public int Value;
}
```

### <a name="create-an-xmlserializer-for-myclass"></a><span data-ttu-id="b1737-137">MyClass에 대한 `XmlSerializer` 만들기</span><span class="sxs-lookup"><span data-stu-id="b1737-137">Create an `XmlSerializer` for MyClass</span></span>

<span data-ttu-id="b1737-138">*Main* 내에 다음 줄을 추가하여 MyClass에 대해 `XmlSerializer`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-138">Add the following line inside *Main* to create an `XmlSerializer` for MyClass:</span></span>

```csharp
var serializer = new System.Xml.Serialization.XmlSerializer(typeof(MyClass));
```

### <a name="build-and-run-the-application"></a><span data-ttu-id="b1737-139">응용 프로그램 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="b1737-139">Build and run the application</span></span>

<span data-ttu-id="b1737-140">*MyApp* 폴더 내에서 [`dotnet run`](../tools/dotnet-run.md)을(를) 통해 응용 프로그램을 실행하면 런타임에 미리 생성된 serializer가 자동으로 로드되어 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-140">Still within the *MyApp* folder, run the application via [`dotnet run`](../tools/dotnet-run.md) and it automatically loads and uses the pre-generated serializers at runtime.</span></span>

<span data-ttu-id="b1737-141">콘솔 창에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-141">Type the following command in your console window:</span></span>

 ```console
 $ dotnet run
 ```
> [!NOTE]
> <span data-ttu-id="b1737-142">[`dotnet run`](../tools/dotnet-run.md)은 [`dotnet build`](../tools/dotnet-build.md)를 호출하여 빌드 대상이 빌드되었는지를 확인하고 `dotnet <assembly.dll>`을 호출하여 대상 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-142">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1737-143">이 자습서에 나와 있는 응용 프로그램 실행을 위한 명령과 단계는 개발하는 동안에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-143">The commands and steps shown in this tutorial to run your application are used during development time only.</span></span> <span data-ttu-id="b1737-144">앱을 배포할 준비가 되면 .NET Core 앱에 대한 여러 [배포 전략](../deploying/index.md) 및 [`dotnet publish`](../tools/dotnet-publish.md) 명령을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="b1737-144">Once you're ready to deploy your app, take a look at the different [deployment strategies](../deploying/index.md) for .NET Core apps and the [`dotnet publish`](../tools/dotnet-publish.md) command.</span></span>

<span data-ttu-id="b1737-145">모든 항목이 성공하면 *MyApp.XmlSerializers.dll*이라는 어셈블리가 출력 폴더에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-145">If everything succeeds, an assembly named *MyApp.XmlSerializers.dll* is generated in the output folder.</span></span> 



<span data-ttu-id="b1737-146">지금까지</span><span class="sxs-lookup"><span data-stu-id="b1737-146">Congratulations!</span></span> <span data-ttu-id="b1737-147">다음 작업을 수행했습니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-147">You have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="b1737-148">.NET Core 앱을 생성했습니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-148">Created a .NET Core app.</span></span>
> * <span data-ttu-id="b1737-149">Microsoft.XmlSerializer.Generator 패키지에 대한 참조를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-149">Added a reference to the Microsoft.XmlSerializer.Generator package.</span></span>
> * <span data-ttu-id="b1737-150">MyApp.csproj를 편집하여 종속성을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-150">Edited your MyApp.csproj to add dependencies.</span></span>
> * <span data-ttu-id="b1737-151">클래스 및 XmlSerializer를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-151">Added a class and an XmlSerializer.</span></span>
> * <span data-ttu-id="b1737-152">응용 프로그램을 빌드하고 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="b1737-152">Built and ran the application.</span></span> 

## <a name="related-resources"></a><span data-ttu-id="b1737-153">관련 참고 자료</span><span class="sxs-lookup"><span data-stu-id="b1737-153">Related Resources</span></span>

* [<span data-ttu-id="b1737-154">XML serialization 소개</span><span class="sxs-lookup"><span data-stu-id="b1737-154">Introducing XML Serialization</span></span>](../../standard/serialization/introducing-xml-serialization.md)
* [<span data-ttu-id="b1737-155">방법: XmlSerializer를 사용하여 serialize(C#)</span><span class="sxs-lookup"><span data-stu-id="b1737-155">How to: Serialize Using XmlSerializer (C#)</span></span>](../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)
* [<span data-ttu-id="b1737-156">방법: XmlSerializer를 사용하여 serialize(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1737-156">How to: Serialize Using XmlSerializer (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)
