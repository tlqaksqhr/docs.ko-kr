---
title: Visual Studio for Mac을 사용하여 macOS에서 완전한 .NET Core 솔루션 빌드
description: 이 항목에서는 재사용 가능한 라이브러리 및 단위 테스트를 포함하는 .NET Core 솔루션을 빌드하는 과정을 안내합니다.
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 01b73fb3ec815440aaf6225f6e7c2894db3d24f2
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="building-a-complete-net-core-solution-on-macos-using-visual-studio-for-mac"></a>Visual Studio for Mac을 사용하여 macOS에서 완전한 .NET Core 솔루션 빌드

Visual Studio for Mac은 .NET Core 응용 프로그램 개발을 위해 필요한 전기능 IDE(통합 개발 환경)를 제공합니다. 이 항목에서는 재사용 가능한 라이브러리 및 단위 테스트를 포함하는 .NET Core 솔루션을 빌드하는 과정을 안내합니다.

이 자습서에서는 사용자가 입력하는 검색어 및 텍스트 문자열을 수락하고, 클래스 라이브러리의 메서드를 사용하여 해당 검색어가 문자열에 나타나는 횟수를 계산하고, 사용자에게 결과를 반환하는 응용 프로그램을 만드는 방법을 보여 줍니다. 또한 이 솔루션에는 TDD(테스트 기반 개발) 개념을 소개하기 위한 클래스 라이브러리용 단위 테스트도 포함되어 있습니다. 전체 샘플에 대한 자습서를 수행하려면 [샘플 솔루션](https://github.com/dotnet/samples/blob/master/core/tutorials/using-on-mac-vs-full-solution/WordCounter)을 다운로드합니다. 다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.

> [!NOTE]
> 사용자 의견은 매우 중요합니다. Mac용 Visual Studio의 개발 팀에 다음 두 가지 방법으로 의견을 제공할 수 있습니다.
> * Mac용 Visual Studio의 메뉴에서 **도움말** > **문제 보고**를 선택하거나 시작 화면에서 **문제 보고**를 선택하면 버그 보고서를 작성하기 위한 창이 열립니다. [Developer Community](https://developercommunity.visualstudio.com/spaces/41/index.html)(개발자 커뮤니티) 포털에서 의견을 추적할 수 있습니다.
> * 제안하려면 메뉴에서 **도움말** > **제안하기**를 선택하거나 시작 화면에서 **제안하기**를 선택합니다. 그러면 [Mac용 Visual Studio UserVoice 웹 페이지](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac)로 이동됩니다.

## <a name="prerequisites"></a>전제 조건

- OpenSSL(.NET Core 1.1을 실행 중인 경우): [Mac에서 .NET Core의 필수 구성 요소](../macos-prerequisites.md) 항목을 참조하세요.
- [.NET Core SDK 1.1 이상](https://www.microsoft.com/net/core#macos)
- [Mac용 visual Studio 2017](https://www.visualstudio.com/vs/visual-studio-mac/)

필수 구성 요소에 대한 자세한 내용은 [Mac의 .NET Core에 대한 필수 구성 요소](../../core/macos-prerequisites.md)를 참조하세요. Mac용 Visual Studio 2017의 전체 시스템 요구 사항은 [Mac용 Visual Studio 2017 제품군 시스템 요구 사항](/visualstudio/productinfo/vs2017-system-requirements-mac)을 참조하세요.

## <a name="building-a-library"></a>라이브러리 빌드

1. 시작 화면에서 **새 프로젝트**를 선택합니다. **새 프로젝트** 대화 상자의 **다중 플랫폼** 노드에서 **.NET 표준 라이브러리** 템플릿을 선택합니다. **새로 만들기**를 선택합니다.

   ![새 프로젝트 대화 상자](./media/using-on-mac-vs-full-solution/vsmacfull01.png)

1. 프로젝트의 이름을 "TextUtils"("텍스트 유틸리티"의 약식 이름)로, 솔루션 이름을 "WordCounter"로 지정합니다. **솔루션 디렉터리 내에 프로젝트 디렉터리를 만드세요.** 를 선택한 상태로 둡니다. **만들기**를 선택합니다.

   ![새 프로젝트 대화 상자](./media/using-on-mac-vs-full-solution/vsmacfull02.png)

1. **솔루션** 사이드바에서 `TextUtils` 노드를 확장하여 템플릿에 제공되는 클래스 파일 *Class1.cs*를 표시합니다. 파일을 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **이름 바꾸기**를 선택한 후 파일 이름을 *WordCount.cs*로 지정합니다. 파일을 열고 내용을 다음 코드로 바꿉니다.

   [!code-csharp[Main](../../../samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter/TextUtils/WordCount.cs)]

1. 세 가지 방법, 즉 바로 가기 키 <kbd>&#8984;</kbd>+<kbd>s</kbd>를 사용하거나, 메뉴에서 **파일** > **저장**을 선택하거나, 파일 탭을 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **저장**을 선택하여 파일을 저장합니다. 다음 그림에서는 IDE 창을 보여 줍니다.

   ![TextUtils 클래스 라이브러리, WordCount 클래스 파일, 정적 클래스 WordCount 및 GetWordCount 메서드를 보여 주는 IDE 창](./media/using-on-mac-vs-full-solution/vsmacfull03.png)

1. IDE 창 아래쪽 여백에서 **오류**를 선택하여 **오류** 패널을 엽니다. **빌드 출력** 단추를 선택합니다.

   ![오류 단추를 표시하는 IDE의 아래쪽 여백](./media/using-on-mac-vs-full-solution/vsmacfull03b.png)

1. 메뉴에서 **빌드** > **모두 빌드**를 선택합니다.

   솔루션이 빌드됩니다. 빌드 출력 패널에 빌드가 성공적으로 수행되었다고 표시됩니다.

   ![빌드 성공 메시지를 표시하는 오류 패널의 빌드 출력 창](./media/using-on-mac-vs-full-solution/vsmacfull04.png)

## <a name="creating-a-test-project"></a>테스트 프로젝트 만들기

단위 테스트는 개발 및 게시 동안 자동화된 소프트웨어 테스트를 제공합니다. 이 자습서에서 사용하는 테스트 프레임워크는 [xUnit(버전 2.2.0 이상)](https://xunit.github.io/)이며, 이는 xUnit 테스트 프로젝트가 다음 단계에서 솔루션에 추가될 때 자동으로 설치됩니다.

1. **솔루션** 사이드바에서 `WordCounter` 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가** > **새 프로젝트 추가**를 선택합니다.

1. **새 프로젝트** 대화 상자의 **.NET Core** 노드에서 **테스트**를 선택합니다. **xUnit 테스트 프로젝트**와 **다음**을 차례로 선택합니다.

   ![xUnit 테스트 프로젝트를 만드는 새 프로젝트 대화 상자](./media/using-on-mac-vs-full-solution/vsmacfull05.png)

1. 새 프로젝트의 이름을 "TestLibrary"로 지정하고 **만들기**를 선택합니다.

   ![프로젝트 이름을 제공하는 새 프로젝트 대화 상자](./media/using-on-mac-vs-full-solution/vsmacfull06.png)

1. 테스트 라이브러리가 `WordCount` 클래스에 대해 작동하도록 하기 위해 `TextUtils` 프로젝트에 대한 참조를 추가합니다. **솔루션** 사이드바에서 **TestLibrary** 아래의 **종속성**을 마우스 오른쪽 단추로 클릭합니다. 상황에 맞는 메뉴에서 **참조 편집**을 선택합니다.

1. **참조 편집** 대화 상자의 **프로젝트** 탭에서 **TextUtils** 프로젝트를 선택합니다. **확인**을 선택합니다.

   ![참조 편집 대화 상자](./media/using-on-mac-vs-full-solution/vsmacfull07.png)

1. **TestLibrary** 프로젝트에서 *UnitTest1.cs* 파일 이름을 *TextUtilsTests.cs*로 바꿉니다.

1. 파일을 열고 코드를 다음으로 바꿉니다.

   ```csharp
   using Xunit;
   using TextUtils;
   using System.Diagnostics;

   namespace TestLibrary
   {
       public class TextUtils_GetWordCountShould
       {
           [Fact]
           public void IgnoreCasing()
           {
               var wordCount = WordCount.GetWordCount("Jack", "Jack jack");
   
               Assert.NotEqual(2, wordCount);
           }
       }
   }
   ```

   다음 이미지는 단위 테스트 코드를 포함하는 IDE를 보여 줍니다. `Assert.NotEqual` 문을 신중히 검토합니다.

   ![IDE 주 창에서 GetWordCount를 확인하기 위한 초기 단위 테스트](./media/using-on-mac-vs-full-solution/vsmacfull08.png)

   TDD를 사용하여 새 테스트를 실패하도록 만들어 테스트 논리가 올바른지 확인하는 것이 중요합니다. 이 메서드는 이름 "Jack"(대문자)과 "Jack" 및 "jack"(대문자 및 소문자)을 포함하는 문자열을 전달합니다. `GetWordCount` 메서드는 제대로 작동하면 검색 단어 인스턴스 2를 반환합니다. 의도적으로 이 테스트가 실패하도록 하기 위해 먼저 검색 단어 "Jack"의 두 인스턴스가 `GetWordCount` 메서드에 의해 반환되지 않음을 어설션하는 테스트를 구현합니다. 다음 단계를 계속 진행하여 의도적으로 이 테스트가 실패하도록 합니다.

1. 화면 오른쪽의 **단위 테스트** 패널을 엽니다.

![단위 테스트 패널](./media/using-on-mac-vs-full-solution/vsmacfull_UnitTestPanel.png)

1. 패널을 열어두려면 **고정** 아이콘을 클릭합니다.

![단위 테스트 패널 고정 아이콘](./media/using-on-mac-vs-full-solution/vsmacfull_UnitTestPanelDockIcon.png)

1. **모두 실행** 단추를 클릭합니다.
   
   테스트가 실패합니다. 이것은 올바른 결과입니다. 테스트 메서드는 `inputString`, "Jack"의 2개 인스턴스가 `GetWordCount` 메서드에 제공된 문자열 "Jack jack"에서 반환되지 않음을 어설션합니다. 단어의 대/소문자가 `GetWordCount` 메서드에서 제외되었으므로 두 개의 인스턴스가 반환됩니다. 2가 2와 *과 같지 않다는* 어설션은 실패합니다. 이것은 올바른 결과이며 테스트 논리는 적합합니다.

   ![테스트 실패](./media/using-on-mac-vs-full-solution/vsmacfull09.png)

1. `Assert.NotEqual`을 `Assert.Equal`로 변경하여 `IgnoreCasing` 테스트 메서드를 수정합니다. 바로 가기 키 <kbd>&#8984;</kbd>+<kbd>s</kbd>와 메뉴의 **파일** > **저장**을 사용하거나 파일 탭을 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **저장**을 선택하여 파일을 저장합니다.

   `inputString` "Jack jack"이 `GetWordCount`로 전달된 상태로 `searchWord` "Jack"은 2개 인스턴스를 반환할 것으로 예상됩니다. **단위 테스트** 패널의 **테스트 실행** 단추 또는 화면 하단에 있는 **테스트 결과** 패널의 **테스트 다시 실행** 단추를 클릭하여 테스트를 다시 실행합니다. 테스트가 통과됩니다. 문자열 "Jack jack"(대/소문자 무시)에는 "Jack" 인스턴스가 2개 있고 테스트 어설션은 `true`입니다.

   ![테스트 통과](./media/using-on-mac-vs-full-solution/vsmacfull10.png)

1. `Fact`를 사용하여 개별 반환 값을 테스트하는 것은 단위 테스트로 수행할 수 있는 작업의 시작일 뿐입니다. 다른 강력한 기법에서는 `Theory`를 사용하여 한 번에 여러 개의 값을 테스트할 수 있습니다. 다음 메서드를 `TextUtils_GetWordCountShould` 클래스에 추가합니다. 이 메서드를 추가한 후 클래스에는 다음 두 개의 메서드가 존재하게 됩니다.

   ```csharp
   [Theory]
   [InlineData(0, "Ting", "Does not appear in the string.")]
   [InlineData(1, "Ting", "Ting appears once.")]
   [InlineData(2, "Ting", "Ting appears twice with Ting.")]
   public void CountInstancesCorrectly(int count, 
                                       string searchWord, 
                                       string inputString)
   {
       Assert.NotEqual(count, WordCount.GetWordCount(searchWord,
                                                  inputString));
   }
   ```

   `CountInstancesCorrectly`는 `GetWordCount` 메서드가 올바르게 계산하는지 확인합니다. `InlineData`는 확인할 개수, 검색 단어 및 입력 문자열을 제공합니다. 테스트 메서드는 데이터의 각 줄에 대해 한 번만 실행됩니다. 데이터에 포함된 개수가 올바르며 해당 값이 `GetWordCount` 메서드에 의해 반환된 개수와 일치한다는 것을 알더라도 `Assert.NotEqual`을 사용하여 먼저 실패를 어설션하는지 한 번 더 확인합니다. 의도적으로 이 테스트가 실패하도록 하는 단계를 수행하는 일이 처음에는 시간 낭비처럼 보일 수 있지만 먼저 실패하여 테스트의 논리를 검토하는 일은 테스트 논리에서 중요한 확인 작업입니다. 실패할 것으로 예상했는데 통과한 테스트 메서드가 나타날 때 테스트 논리에서 버그가 발견되었습니다. 테스트 메서드를 만들 때마다 이 단계를 수행하는 것은 가치 있는 일입니다.
   
1. 파일을 저장하고 테스트를 다시 실행합니다. 대/소문자 구분 테스트는 통과하지만 세 가지 계산 테스트는 실패합니다. 이것은 예상하던 동작입니다.

   ![테스트 실패](./media/using-on-mac-vs-full-solution/vsmacfull11.png)

1. `Assert.NotEqual`을 `Assert.Equal`로 변경하여 `CountInstancesCorrectly` 테스트 메서드를 수정합니다. 파일을 저장합니다. 테스트를 다시 실행합니다. 모든 테스트가 통과됩니다.

   ![테스트 통과](./media/using-on-mac-vs-full-solution/vsmacfull12.png)

## <a name="adding-a-console-app"></a>콘솔 앱 추가

1. **솔루션** 사이드바에서 `WordCounter` 솔루션을 마우스 오른쪽 단추로 클릭합니다. **.NET Core** > **앱** 템플릿에서 템플릿을 선택하여 새 **콘솔 응용 프로그램** 프로젝트를 추가합니다. **새로 만들기**를 선택합니다. 프로젝트 이름을 **WordCounterApp**으로 지정합니다. **만들기**를 선택하여 솔루션에 프로젝트를 만듭니다.

1. **솔루션** 사이드바에서 새 **WordCounterApp** 프로젝트에서 **종속성**을 마우스 오른쪽 단추로 클릭합니다. **참조 편집** 대화 상자에서 **TextUtils**를 선택하고 **확인**을 선택합니다.

1. *Program.cs* 파일을 엽니다. 코드를 다음으로 바꿉니다.

   [!code-csharp[Main](../../../samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter/WordCounterApp/Program.cs)]

1. IDE 대신 콘솔 창에는 앱을 실행하려면 `WordCounterApp` 프로젝트를 마우스 오른쪽 단추로 클릭하고 **옵션**을 선택한 후 **구성** 아래에서 **기본값** 노드를 엽니다. **외부 콘솔에서 실행** 확인란을 선택합니다. **콘솔 출력 일시 중지** 옵션을 선택한 상태로 둡니다. 이 설정을 사용하면 앱이 콘솔 창에 생성되므로 `Console.ReadLine` 문에 대한 입력을 입력할 수 있습니다. 앱이 IDE에서 실행되도록 하면 `Console.WriteLine` 문의 출력을 볼 수만 있습니다. `Console.ReadLine` 문은 **응용 프로그램 출력** 패널에서 작동하지 않습니다.

   ![프로젝트 옵션 창](./media/using-on-mac-vs-full-solution/vsmacfull13.png)

1. 현재 Mac용 Visual Studio 현재 버전은 솔루션이 실행될 때 테스트를 실행할 수 없으므로 콘솔 앱을 직접 실행합니다. `WordCounterApp` 프로젝트를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **항목 실행**을 선택합니다. 재생 단추를 사용하여 앱을 실행하려고 하면 Test Runner 및 앱이 실행되지 못합니다. 이 문제와 관련된 작업의 상태에 대한 자세한 내용은 [xunit/xamarinstudio.xunit (#60)](https://github.com/xunit/xamarinstudio.xunit/issues/60)을 참조하세요. 앱을 실행할 때 콘솔 창의 프롬프트에 검색 단어 및 입력 문자열 값을 제공합니다. 앱은 문자열에서 검색 단어가 표시되는 횟수를 나타냅니다.

   ![문자열 'Iro ate olives by the lake, and the olives were wonderful.'에서 검색된 단어 olives를 보여 주는 콘솔 창 앱은 'The search word olives appears 2 times.'로 응답함](./media/using-on-mac-vs-full-solution/vsmacfull14.png)

1. 알아보려는 마지막 기능은 Visual Studio for Mac을 사용한 디버깅입니다. `Console.WriteLine` 문에서 중단점을 설정합니다. 줄 23의 왼쪽 여백을 선택하면 코드 줄 옆에 빨간색 원이 표시되는 것을 볼 수 있습니다. 또는 코드 줄의 아무 위치나 선택하고 메뉴에서 **실행** > **중단점 설정/해제**를 선택합니다.

   ![중단점은 줄 23, Console.WriteLine 문에 설정됨](./media/using-on-mac-vs-full-solution/vsmacfull15.png)

1. `WordCounterApp` 프로젝트를 마우스 오른쪽 단추로 클릭합니다. 상황에 맞는 메뉴에서 **디버깅 시작** 항목을 선택합니다. 앱이 실행될 때 검색 단어 "cat" 및 검색할 문자열 "The dog chased the cat, but the cat escaped."를 입력합니다. `Console.WriteLine` 문에 도달하면 프로그램 실행이 중단된 후 해당 문이 실행됩니다. **지역** 탭에 `searchWord`, `inputString`, `wordCount` 및 `pluralChar` 값이 표시될 수 있습니다.

   ![Console.WriteLine 문에서 프로그램 실행이 중지되고 지역 창에 값이 표시된 직후에 Console.WriteLine 문이 실행됩니다.](./media/using-on-mac-vs-full-solution/vsmacfull16.png)

1. **직접 실행** 창에서 "wordCount = 999;"를 입력하고 Enter 키를 누릅니다. 이렇게 하면 의미 없는 값인 999가 `wordCount` 변수에 할당되면서 디버그 동안 변수 값을 바꿀 수 있음을 보여 줍니다.

   ![중단점이 적중됩니다. 직접 실행 창에서 wordCount가 값 999로 변경됨](./media/using-on-mac-vs-full-solution/vsmacfull17.png)

1. 도구 모음에서 *계속* 화살표를 클릭합니다. 콘솔 창에서 출력을 봅니다. 앱을 디버그할 때 설정한 잘못된 값인 999가 보고됩니다.

   ![도구 모음의 계속 단추](./media/using-on-mac-vs-full-solution/vsmacfull18.png)

   ![앱 출력에서 검색 단어 개수가 값 999로 변경됨](./media/using-on-mac-vs-full-solution/vsmacfull19.png)

## <a name="see-also"></a>참고 항목

[Mac용 Visual Studio 2017 릴리스 정보](/visualstudio/releasenotes/vs2017-mac-relnotes)
