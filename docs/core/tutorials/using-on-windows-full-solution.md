---
title: Visual Studio 2017을 사용하여 Windows에서 완전한 .NET Core 솔루션 구축
description: Windows의 Visual Studio 2017에서 완전한 .NET Core 솔루션을 구축하는 방법에 관해 알아봅니다.
author: bleroy
ms.author: mairaw
ms.date: 11/16/2016
ms.openlocfilehash: 52b8781cdc29ac776123402c982353ef437ce74f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33214395"
---
# <a name="building-a-complete-net-core-solution-on-windows-using-visual-studio-2017"></a>Visual Studio 2017을 사용하여 Windows에서 완전한 .NET Core 솔루션 구축

Visual Studio 2017은 .NET Core 응용 프로그램 개발을 위해 필요한 모든 기능을 갖춘 개발 환경을 제공합니다. 이 문서의 절차에서는 재사용 가능한 라이브러리, 테스트 및 타사 라이브러리 사용을 비롯하여 일반적인 .NET Core 솔루션을 빌드하는 데 필요한 단계를 설명합니다. 

## <a name="prerequisites"></a>전제 조건

[필수 조건 페이지](../windows-prerequisites.md)의 지침에 따라 환경을 업데이트합니다.

## <a name="a-solution-using-only-net-core-projects"></a>.NET Core 프로젝트만을 사용하는 솔루션

### <a name="writing-the-library"></a>라이브러리 작성

1. Visual Studio에서 **파일**, **새로 만들기**, **프로젝트**를 선택합니다. **새 프로젝트** 대화 상자에서 **Visual C#** 노드를 확장하고 **.NET Standard** 노드를 선택한 다음 **클래스 라이브러리(.NET Standard)** 를 선택합니다. 

2. 프로젝트 이름을 "Library", 솔루션 이름을 "Golden"으로 지정합니다. **솔루션용 디렉터리 만들기** 확인란을 선택한 상태로 둡니다. **확인**을 클릭합니다.

3. 솔루션 탐색기에서 **종속성** 노드의 상황에 맞는 메뉴를 열고 **NuGet 패키지 관리**를 선택합니다.

4. **패키지 소스**로 "nuget.org"를 선택하고 **찾아보기** 탭을 선택합니다. **Newtonsoft.Json**을 찾습니다. **설치**를 클릭하고 사용권 계약에 동의합니다. 이제 패키지에 **종속성/NuGet**이 표시되며 자동으로 복원됩니다.

5. `Class1.cs` 파일이 이름을 `Thing.cs`로 바꿉니다. 클래스의 이름 바꾸기를 적용합니다. 메서드 추가: `public int Get(int number) => Newtonsoft.Json.JsonConvert.DeserializeObject<int>($"{number}");`

7. **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.

   솔루션이 오류 없이 빌드됩니다.

### <a name="writing-the-test-project"></a>테스트 프로젝트 작성

1. 솔루션 탐색기에서 **솔루션** 노드의 상황에 맞는 메뉴를 열고 **추가**, **새 프로젝트**를 차례로 선택합니다. **새 프로젝트** 대화 상자에서 **Visual C# / .NET Core**를 선택하고 **단위 테스트 프로젝트(.NET Core)** 를 선택합니다. 이름을 "TestLibrary"로 지정하고 [확인]을 클릭합니다. 

2. **TestLibrary** 프로젝트에서 **종속성** 노드의 상황에 맞는 메뉴를 열고 **참조 추가**를 선택합니다. **프로젝트**를 클릭한 다음 라이브러리 프로젝트를 확인한 후 [확인]을 클릭합니다. 이렇게 하면 테스트 프로젝트에 라이브러리에 대한 참조가 추가됩니다.

3. `UnitTest1.cs` 파일의 이름을 `LibraryTests.cs`로 바꾸고 클래스 이름 바꾸기를 허용합니다. 파일 맨 위에 `using Library;`를 추가하고 `TestMethod1` 메서드를 다음 코드로 바꿉니다.
    ```csharp
    [TestMethod]
    public void ThingGetsObjectValFromNumber()
    {
        Assert.AreEqual(42, new Thing().Get(42));
    }
    ```

   이제 솔루션을 빌드할 수 있습니다. 
   
4. 작업 영역에 테스트 탐색기 창을 가져오도록 **테스트** 메뉴에서 **Windows**, **테스트 탐색기**를 선택합니다. 몇 초 후에 `ThingGetsObjectValFromNumber` 테스트가 테스트 탐색기에 표시됩니다. **모두 실행**을 선택합니다.
   
   테스트를 전달해야 합니다.

### <a name="writing-the-console-app"></a>콘솔 앱 작성

1. 솔루션 탐색기에서 솔루션의 상황에 맞는 메뉴를 열고 새 **콘솔 앱(.NET Core)** 프로젝트를 추가합니다. "App"으로 이름을 지정합니다.

2. **App** 프로젝트에서 **종속성** 노드의 상황에 맞는 메뉴를 열고 **추가**, **참조**를 선택합니다. 

3. **참조 관리자** 대화 상자에서 **프로젝트** 아래에 있는 **라이브러리**, **솔루션** 노드를 선택한 후 **확인**을 클릭합니다.

6. **앱** 노드의 상황에 맞는 메뉴를 열고 **시작 프로젝트로 설정**을 선택합니다. F5 또는 CTRL + F5 키를 눌러 콘솔 앱이 시작됩니다.

7. `Program.cs` 파일을 열고 `using Library;` 지시문을 파일의 상단에 추가한 다음 `Console.WriteLine($"The answer is {new Thing().Get(42)}.");`을 `Main` 메서드에 추가합니다.

8. 방금 추가한 줄 뒤에 중단점을 설정합니다.

9. F5 키를 눌러 응용 프로그램을 실행합니다.

   응용 프로그램이 오류 없이 빌드되고 중단점에 도달합니다. 또한 응용 프로그램 출력이 "The answer is 42."인지 확인할 수 있습니다.
