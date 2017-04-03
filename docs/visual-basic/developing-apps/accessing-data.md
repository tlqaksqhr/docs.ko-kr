---
title: "Visual Basic 응용 프로그램에서 데이터에 액세스 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- data [Visual Basic]
- Visual Basic, data access
ms.assetid: 3086ab38-3be5-4b22-9385-7d0e16b04f6a
caps.latest.revision: 23
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 01c5dfdd118d1db9adfd1c8e83c3ed63348e4c43
ms.lasthandoff: 03/13/2017

---
# <a name="accessing-data-in-visual-basic-applications"></a>Visual Basic 응용 프로그램에서 데이터에 액세스
[!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에는 데이터에 액세스하는 응용 프로그램 개발을 지원하기 위한 여러 가지 새로운 기능이 포함됩니다. [데이터 소스 창](https://docs.microsoft.com/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)에서 양식으로 항목을 끌어 Windows 응용 프로그램에 대한 데이터 바인딩된 양식을 만듭니다. **데이터 소스 창**에서 기존 컨트롤로 항목을 끌어 컨트롤을 데이터에 바인딩합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [데이터 응용 프로그램 만들기](https://docs.microsoft.com/visualstudio/data-tools/creating-data-applications)  
 응용 프로그램에 데이터 액세스 기능을 통합하는 방법을 설명하는 페이지의 링크를 제공합니다.

 [Visual Studio의 데이터 응용 프로그램 개요](https://docs.microsoft.com/visualstudio/data-tools/overview-of-data-applications-in-visual-studio)  
 [!INCLUDE[vsprvs](../../csharp/includes/vsprvs_md.md)]를 통해 데이터를 사용하는 응용 프로그램을 만드는 방법에 대한 페이지의 링크를 제공합니다.  
  
 [LINQ](../../visual-basic/programming-guide/language-features/linq/index.md)  
 Visual Basic에서 LINQ를 사용하는 방법을 설명하는 항목의 링크를 제공합니다.  
  
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)  
 [!INCLUDE[vbtecdlinq](../../csharp/includes/vbtecdlinq_md.md)]에 대한 정보를 제공합니다. 프로그래밍 예제를 포함합니다.  
  
 [LINQ to SQL Tools in Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)(Visual Studio의 LINQ to SQL 도구)  
 응용 프로그램에서 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) 개체 모델을 만드는 방법에 대한 항목의 링크를 제공합니다.  
  
 [n 계층 응용 프로그램에서 데이터 집합 작업](https://docs.microsoft.com/visualstudio/data-tools/work-with-datasets-in-n-tier-applications)  
 다중 계층 데이터 응용 프로그램을 만드는 방법에 대한 항목의 링크를 제공합니다.  
     
 [Visual Studio에서 데이터에 연결](https://docs.microsoft.com/visualstudio/data-tools/connecting-to-data-in-visual-studio)  
 [!INCLUDE[vsprvs](../../csharp/includes/vsprvs_md.md)]를 사용하여 디자인 타임 도구 및 ADO.NET 연결 개체를 통해 응용 프로그램을 데이터에 연결하는 방법에 대한 페이지의 링크를 제공합니다.  

 [데이터를 응용 프로그램으로 페치](https://docs.microsoft.com/visualstudio/data-tools/fetching-data-into-your-application)  
 데이터를 데이터 집합에 로드하는 방법 및 SQL 문과 저장 프로시저를 실행하는 방법을 설명하는 페이지의 링크를 제공합니다.  
  
 [Visual Studio에서 데이터에 컨트롤 바인딩](https://docs.microsoft.com/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)  
 데이터 바인딩된 컨트롤을 통해 Windows Forms에 데이터를 표시하는 방법을 설명하는 페이지의 링크를 제공합니다.  
  
 [응용 프로그램에서 데이터 편집](https://docs.microsoft.com/visualstudio/data-tools/editing-data-in-your-application)  
 데이터 집합의 데이터 테이블에서 데이터를 조작하는 방법을 설명하는 페이지의 링크를 제공합니다.  
  
 [데이터 집합의 데이터 유효성 검사](https://docs.microsoft.com/visualstudio/data-tools/validate-data-in-datasets)  
 열 및 행 변경 중에 데이터 집합에 유효성 검사를 추가하는 방법을 설명하는 페이지의 링크를 제공합니다.  
  
 [데이터 저장](https://docs.microsoft.com/visualstudio/data-tools/saving-data)  
 응용 프로그램에서 데이터베이스로 업데이트된 데이터를 보내는 방법을 설명하는 페이지의 링크를 제공합니다.  
  
 [ADO.NET](https://msdn.microsoft.com/library/e80y5yhx.aspx)  
 .NET Framework 프로그래머에게 데이터 액세스 서비스를 표시하는 ADO.NET 클래스에 대해 설명합니다.

 [Office 솔루션의 데이터](https://msdn.microsoft.com/library/xx069ybh)  
 스키마 지향 프로그래밍, 데이터 캐싱 및 서버 쪽 데이터 액세스에 대한 정보를 비롯하여 Office 솔루션에서 데이터가 작동하는 방법을 설명하는 페이지의 링크가 포함되어 있습니다.
