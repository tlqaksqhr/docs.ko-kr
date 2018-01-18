---
title: "방법: Visual Studio에서 LINQ to DataSet 프로젝트 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 3add191250a10d1d6016263ada0ba53fc8082717
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a>방법: Visual Studio에서 LINQ to DataSet 프로젝트 만들기
다양한 형식의 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 프로젝트에는 가져온 네임스페이스(Visual Basic) 또는 `using` 지시문(C#) 및 참조가 필요합니다. 적어도 System.Core.dll에 대한 참조와 `using`에 대한 <xref:System.Linq> 지시문이 있어야 합니다. 기본적으로 이들은 새 [!INCLUDE[csharp_orcas_long](../../../../includes/csharp-orcas-long-md.md)] 프로젝트를 만들면 제공됩니다. 또한 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]에는 System.Data.dll 및 System.Data.DataSetExtensions.dll에 대한 참조와 `Imports`(Visual Basic) 또는 `using`(C#) 지시문이 필요합니다.  
  
 이전 버전의 Visual Studio에서 만든 프로젝트를 업그레이드하는 경우 이러한 LINQ 관련 참조를 직접 제공해야 합니다. 또한 .NET Framework 버전 3.5를 대상으로 프로젝트를 직접 설정해야 합니다.  
  
> [!NOTE]
>  LINQ 관련 Dll을 직접 참조 해야 명령 프롬프트에서 작성 하는 경우 `drive` **:**\Program Files\Reference Assemblies\Microsoft\Framework\v3.5 합니다.  
  
### <a name="to-target-the-net-framework-35"></a>.NET Framework 3.5를 대상으로 지정하려면  
  
1.  [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]에서 새 Visual Basic 또는 C# 프로젝트를 만듭니다. 또는 Visual Studio 2005에서 만든 Visual Basic 또는 C# 프로젝트를 열고 프롬프트에 따라 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 프로젝트로 변환할 수 있습니다.  
  
2.  C# 프로젝트에 대 한 클릭는 **프로젝트** 메뉴를 차례로 클릭 **속성**합니다.  
  
    1.  에 **응용 프로그램** 속성 페이지에서.NET Framework 3.5를 선택는 **대상 프레임 워크** 드롭 다운 목록입니다.  
  
3.  Visual Basic 프로젝트를 클릭 하 고 **프로젝트** 메뉴를 차례로 클릭 **속성**합니다.  
  
    1.  에 **컴파일** 속성 페이지에서 클릭 **고급 컴파일 옵션** 다음에서.NET Framework 3.5를 선택 하 고는 **대상 프레임 워크 (모든 구성)** 드롭 다운 목록입니다.  
  
4.  에 **프로젝트** 메뉴를 클릭 **참조 추가**, 클릭는 **.NET** 탭에서 아래쪽으로 스크롤하여 **System.Core**,를 클릭 한 다음 를클릭 **정상**합니다.  
  
5.  `using`에 대한 <xref:System.Linq> 지시문 또는 가져온 네임스페이스를 소스 코드 파일이나 프로젝트에 추가합니다.  
  
     자세한 내용은 참조 [지시문을 사용 하 여](~/docs/csharp/language-reference/keywords/using-directive.md) 또는 [하는 방법: 추가 또는 제거 (Visual Basic) 가져온 네임 스페이스](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)합니다.  
  
### <a name="to-enable-linq-to-dataset-functionality"></a>LINQ to DataSet 기능을 사용하려면  
  
1.  필요한 경우 이 항목의 앞에서 설명한 단계에 따라 System.Core.dll에 대한 참조와 System.Linq에 대한 `using` 지시문 또는 가져온 네임스페이스를 추가합니다.  
  
2.  C# 또는 Visual Basic:는 **프로젝트** 메뉴를 차례로 클릭 **참조 추가**합니다.  
  
3.  에 **참조 추가** 대화 상자를 클릭는 **.NET** 탭 위에 표시 되지 않은 경우. 으로 아래로 스크롤하여 **System.Data** 및 **System.Data.DataSetExtensions** 찾아서 클릭 합니다. 클릭는 **확인** 단추입니다.  
  
4.  `using`에 대한 <xref:System.Data> 지시문 또는 가져온 네임스페이스를 소스 코드 파일이나 프로젝트에 추가합니다. 자세한 내용은 참조 [지시문을 사용 하 여](~/docs/csharp/language-reference/keywords/using-directive.md) 또는 [하는 방법: 추가 또는 제거 (Visual Basic) 가져온 네임 스페이스](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)합니다.  
  
5.  LINQ to Dataset 기능을 위해 System.Data.DataSetExtensions.dll에 대한 참조를 추가합니다. System.Data.dll에 대한 참조가 아직 없으면 해당 참조를 추가합니다.  
  
6.  데이터베이스에 연결하는 방법에 따라 선택적으로 `using` 또는 `System.Data.Common`에 대한 `System.Data.SqlClient` 지시문 또는 가져온 네임스페이스를 추가합니다.  
  
## <a name="see-also"></a>참고 항목  
 [시작](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
 [LINQ 시작](http://msdn.microsoft.com/en-us/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9)
