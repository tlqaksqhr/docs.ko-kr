---
title: "기본적인 문자열 작업"
description: "기본적인 문자열 작업"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 9658098d-de60-4868-ba5b-0c278748a90f
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: b8bdbeccd226c412e725200fcaf81ec568afc5bc
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="basic-string-operations"></a><span data-ttu-id="df9f7-104">기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="df9f7-104">Basic string operations</span></span>

<span data-ttu-id="df9f7-105">응용 프로그램에서 사용자 입력을 기반으로 메시지를 생성하여 사용자에게 응답하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="df9f7-105">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="df9f7-106">예를 들어 웹 사이트에서 사용자 이름을 포함하는 특수 인사말을 사용하여 새로 로그온한 사용자에게 응답하는 경우도 드물지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df9f7-106">For example, it is not uncommon for Web sites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span> <span data-ttu-id="df9f7-107">[System.String](xref:System.String) 및 [System.Text.StringBuilder](xref:System.Text.StringBuilder) 클래스의 여러 메서드를 통해 사용자 인터페이스에 표시할 사용자 지정 문자열을 동적으로 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df9f7-107">Several methods in the [System.String](xref:System.String) and [System.Text.StringBuilder](xref:System.Text.StringBuilder) classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="df9f7-108">이러한 메서드는 바이트 배열에서 새 문자열 만들기, 문자열 값 비교, 기존 문자열 수정 등의 여러 기본적인 문자열 작업을 수행하는 데에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df9f7-108">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="df9f7-109">단원 내용</span><span class="sxs-lookup"><span data-stu-id="df9f7-109">In This Section</span></span>

<span data-ttu-id="df9f7-110">[새 문자열 만들기](creating-new.md) - 개체를 문자열로 변환하고 문자열을 결합하는 기본적인 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="df9f7-110">[Creating new strings](creating-new.md) - Describes basic ways to convert objects into strings and to combine strings.</span></span>

<span data-ttu-id="df9f7-111">[문자 트리밍 및 제거](trimming.md) - 문자열의 문자를 트리밍하거나 제거하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="df9f7-111">[Trimming and removing characters](trimming.md) - Describes how to trim or remove characters in a string.</span></span> 

<span data-ttu-id="df9f7-112">[문자열 채우기](padding.md) - 문자열에 문자 또는 공백을 삽입하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="df9f7-112">[Padding strings](padding.md) - Describes how to insert characters or empty spaces into a string.</span></span>

<span data-ttu-id="df9f7-113">[문자열 비교](comparing.md) - 둘 이상의 문자열 내용을 비교하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="df9f7-113">[Comparing strings](comparing.md) - Describes how to compare the contents of two or more strings.</span></span>

<span data-ttu-id="df9f7-114">[대/소문자 변경](changing-case.md) - 문자열 내 문자의 대/소문자를 변경하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="df9f7-114">[Changing case](changing-case.md) - Describes how to change the case of characters within a string.</span></span>

<span data-ttu-id="df9f7-115">[StringBuilder 클래스 사용](stringbuilder.md) - [StringBuilder](xref:System.Text.StringBuilder) 클래스를 사용하여 동적 문자열 개체를 만들고 수정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="df9f7-115">[Using the StringBuilder class](stringbuilder.md) - Describes how to create and modify dynamic string objects with the [StringBuilder](xref:System.Text.StringBuilder) class.</span></span>

<span data-ttu-id="df9f7-116">[방법: 기본적인 문자열 조작 수행](basic-manipulations.md) - 기본적인 문자열 작업의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="df9f7-116">[How to: Perform basic string manipulations](basic-manipulations.md) - Demonstrates the use of basic string operations.</span></span>

## <a name="related-sections"></a><span data-ttu-id="df9f7-117">관련 단원</span><span class="sxs-lookup"><span data-stu-id="df9f7-117">Related Sections</span></span>

<span data-ttu-id="df9f7-118">[형식 변환](type-conversion.md) - 형식 간에 변환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="df9f7-118">[Type conversion](type-conversion.md) - Describes how to convert from one type to another.</span></span>

<span data-ttu-id="df9f7-119">[형식 서식 지정](formatting-types.md) - 문자열 형식 지정자를 사용하여 문자열 형식을 지정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="df9f7-119">[Formatting types](formatting-types.md) - Describes how to format strings using the string format specifiers.</span></span>



