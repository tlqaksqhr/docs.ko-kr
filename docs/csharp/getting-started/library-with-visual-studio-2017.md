---
title: "Visual Studio 2017에서 C# 및 .NET Core로 클래스 라이브러리 빌드"
description: "Visual Studio 2017을 사용하여 C#으로 작성된 클래스 라이브러리를 빌드하는 방법 알아보기"
keywords: ".NET Core, .NET 표준 클래스 라이브러리, Visual Studio 2017"
author: stevehoag
ms.author: shoag
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: c849ca26-6a25-4d35-9544-f343af88e0e7
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 28fa60cdcf8e0056314af271208759eadd8503a5
ms.lasthandoff: 03/13/2017

---

# <a name="building-a-class-library-with-c-and-net-core-in-visual-studio-2017"></a>Visual Studio 2017에서 C# 및 .NET Core로 클래스 라이브러리 빌드 #

클래스 라이브러리는 어떤 응용 프로그램에서도 호출할 수 있는 형식 및 메서드를 정의합니다. .NET Core를 사용하여 개발한 클래스 라이브러리는 .NET 표준 라이브러리를 지원하므로 .NET 표준 라이브러리의 해당 버전을 지원하는 모든 .NET 플랫폼에서 라이브러리를 호출할 수 있습니다. 클래스 라이브러리를 마치면 타사 구성 요소를 배포할 것인지 또는 하나 이상의 응용 프로그램과 함께 번들로 제공되는 구성 요소로 포함시킬지를 결정할 수 있습니다.

> [!NOTE]
> .NET 표준 버전 및 지원되는 플랫폼 목록은 [.NET 표준 라이브러리](../../standard/library.md)를 참조하세요.

이 항목에서는 단일 문자열 처리 메서드를 포함하는 간단한 유틸리티 라이브러리를 만들어 보겠습니다. 마치 @System.String 클래스의 멤버처럼 호출할 수 있게 [확장 메서드](../../csharp/programming-guide/classes-and-structs/extension-methods.md)로 구현합니다.

## <a name="creating-a-class-library-solution"></a>클래스 라이브러리 솔루션 만들기 ##

먼저 클래스 라이브러리 프로젝트의 솔루션과 관련 프로젝트를 만들어 보겠습니다. Visual Studio 솔루션은 하나 이상의 프로젝트에 대한 컨테이너로 작동합니다. 솔루션을 만들려면

1. Visual Studio 메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택합니다.

1. 다음 그림과 같이 **새 프로젝트** 대화 상자에서 **기타 프로젝트 형식** 노드를 확장하고 **Visual Studio 솔루션**을 선택합니다.

   ![이미지](./media/solution.jpg)

1. 솔루션의 이름을 "ClassLibraryProjects"로 지정하고 **확인** 단추를 선택합니다. 다음 그림에서는 결과를 보여 줍니다.

   ![이미지](./media/vs_with_solution.jpg)

## <a name="creating-the-class-library-project"></a>클래스 라이브러리 프로젝트 만들기 ##

이제 클래스 라이브러리 프로젝트를 만들 수 있습니다.

1. **솔루션 탐색기**에서 **ClassLibraryProjects** 노드에 대한 상황에 맞는 메뉴를 열고 **추가**, **새 프로젝트**를 선택합니다.

1. **새 프로젝트 추가** 대화 상자에서 **.NET Core** 노드를 선택하고 **클래스 라이브러리(.NET 표준)** 프로젝트 템플릿을 선택합니다.

1. 다음 그림과 같이 **이름** 텍스트 상자에 프로젝트 이름으로 "StringLibrary"를 입력합니다.

   ![이미지](./media/lib_project.jpg)

1. **확인**을 선택하여 클래스 라이브러리 프로젝트를 만듭니다. 다음 그림에서는 결과를 보여 줍니다.

   ![이미지](./media/class_library.jpg)

1. 코드 창의 코드를 다음 코드로 바꿉니다.

   [!CODE-csharp[ClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs#1)]

   클래스 라이브러리 `UtilityLibraries.StringLibrary`에는 `StartsWithUpper`라는 메서드가 포함됩니다. 이 메서드는 현재 문자열 인스턴스가 대문자로 시작하는지 여부를 나타내는 @System.Boolean 값을 반환합니다. 대문자로 나타내는 문자는 유니코드 표준에 따라 정의됩니다. .NET Core에서는 [Char.IsUpper](xref:System.Char.IsUpper(System.Char)) 메서드는 문자가 대문자이면 `true`를 반환합니다.

1. 메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다. 프로젝트가 오류 없이 컴파일되어야 합니다.

## <a name="the-next-step"></a>다음 단계 ##

지금까지 라이브러리를 성공적으로 빌드했습니다. 그렇지만 어떤 메서드도 호출하지 않았으므로 예상대로 작동하는지 알지 못합니다. 라이브러리 개발의 다음 단계는 [C# 단위 테스트 프로젝트](testing-library-with-visual-studio.md)를 사용하여 테스트하는 것입니다.



