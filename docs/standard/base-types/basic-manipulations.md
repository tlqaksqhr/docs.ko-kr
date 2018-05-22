---
title: '방법: .NET Framework의 기본 문자열 조작 수행'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET Framework], examples
ms.assetid: 121d1eae-251b-44c0-8818-57da04b8215e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e8c6c3f9b7ec418fdbf6365a3e7d90fe65e9caa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-perform-basic-string-manipulations-in-net"></a><span data-ttu-id="94ff1-102">방법: .NET에서 기본적인 문자열 조작 수행</span><span class="sxs-lookup"><span data-stu-id="94ff1-102">How to: Perform Basic String Manipulations in .NET</span></span>
<span data-ttu-id="94ff1-103">다음 예제에서는 [기본적인 문자열 작업](../../../docs/standard/base-types/basic-string-operations.md) 항목에 설명된 메서드 중 일부를 사용하여 실제 응용 프로그램에서 발견될 수 있는 방식으로 문자열 조작을 수행하는 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="94ff1-103">The following example uses some of the methods discussed in the [Basic String Operations](../../../docs/standard/base-types/basic-string-operations.md) topics to construct a class that performs string manipulations in a manner that might be found in a real-world application.</span></span> <span data-ttu-id="94ff1-104">`MailToData` 클래스는 개인의 이름과 주소를 별도 속성에 저장하고 `City`, `State` 및 `Zip` 필드를 사용자에게 표시할 단일 문자열로 결합하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="94ff1-104">The `MailToData` class stores the name and address of an individual in separate properties and provides a way to combine the `City`, `State`, and `Zip` fields into a single string for display to the user.</span></span> <span data-ttu-id="94ff1-105">또한 이 클래스를 사용하면 사용자가 구/군/시, 시/도 및 우편 번호 정보를 단일 문자열로 입력할 수 있습니다. 응용 프로그램에서 단일 문자열을 자동으로 구문 분석하고 해당 속성에 적절한 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="94ff1-105">Furthermore, the class allows the user to enter the city, state, and ZIP Code information as a single string; the application automatically parses the single string and enters the proper information into the corresponding property.</span></span>  
  
 <span data-ttu-id="94ff1-106">편의상, 이 예제에서는 명령줄 인터페이스가 있는 콘솔 응용 프로그램을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="94ff1-106">For simplicity, this example uses a console application with a command-line interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94ff1-107">예</span><span class="sxs-lookup"><span data-stu-id="94ff1-107">Example</span></span>  
 [!code-csharp[Conceptual.String.BasicOps#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/basicops.cs#1)]
 [!code-vb[Conceptual.String.BasicOps#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/basicops.vb#1)]  
  
 <span data-ttu-id="94ff1-108">앞의 코드를 실행하면 사용자 이름과 주소를 입력하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="94ff1-108">When the preceding code is executed, the user is asked to enter his or her name and address.</span></span> <span data-ttu-id="94ff1-109">응용 프로그램은 해당 속성에 정보를 저장하고 구/군/시, 시/도 및 우편 번호 정보를 표시하는 단일 문자열을 만들어 사용자에게 다시 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="94ff1-109">The application places the information in the appropriate properties and displays the information back to the user, creating a single string that displays the city, state, and ZIP Code information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94ff1-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94ff1-110">See Also</span></span>  
 [<span data-ttu-id="94ff1-111">기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="94ff1-111">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)
