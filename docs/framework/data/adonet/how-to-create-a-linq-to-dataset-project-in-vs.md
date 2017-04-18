---
title: "방법: Visual Studio에서 LINQ to DataSet 프로젝트 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 방법: Visual Studio에서 LINQ to DataSet 프로젝트 만들기
다양한 형식의 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 프로젝트에는 가져온 네임스페이스\(Visual Basic\) 또는 `using` 지시문\(C\#\) 및 참조가 필요합니다.  적어도 System.Core.dll에 대한 참조와 <xref:System.Linq>에 대한 `using` 지시문이 있어야 합니다.  기본적으로 이들은 새 [!INCLUDE[csharp_orcas_long](../../../../includes/csharp-orcas-long-md.md)] 프로젝트를 만들면 제공됩니다.  또한 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]에는 System.Data.dll 및 System.Data.DataSetExtensions.dll에 대한 참조와 `Imports`\(Visual Basic\) 또는 `using`\(C\#\) 지시문이 필요합니다.  
  
 이전 버전의 Visual Studio에서 만든 프로젝트를 업그레이드하는 경우 이러한 LINQ 관련 참조를 직접 제공해야 합니다.  또한 .NET Framework 버전 3.5를 대상으로 프로젝트를 직접 설정해야 합니다.  
  
> [!NOTE]
>  명령 프롬프트에서 빌드하는 경우 `drive`**:**\\Program Files\\Reference Assemblies\\Microsoft\\Framework\\v3.5에 있는 LINQ 관련 DLL을 직접 참조해야 합니다.  
  
### .NET Framework 3.5를 대상으로 지정하려면  
  
1.  [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]에서 새 Visual Basic 또는 C\# 프로젝트를 만듭니다. 또는 Visual Studio 2005에서 만든 Visual Basic 또는 C\# 프로젝트를 열고 프롬프트에 따라 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 프로젝트로 변환할 수 있습니다.  
  
2.  C\# 프로젝트의 경우 **프로젝트** 메뉴를 클릭한 다음 **속성**을 클릭합니다.  
  
    1.  **응용 프로그램** 속성 페이지의 **대상 프레임워크** 드롭다운 목록에서 .NET Framework 3.5를 선택합니다.  
  
3.  Visual Basic 프로젝트의 경우 **프로젝트** 메뉴를 클릭한 다음 **속성**을 클릭합니다.  
  
    1.  **컴파일** 속성 페이지에서 **고급 컴파일 옵션**을 클릭한 다음 **대상 프레임워크\(모든 구성\)** 드롭다운 목록에서 .NET Framework 3.5를 선택합니다.  
  
4.  **프로젝트** 메뉴에서 **참조 추가**, **.NET** 탭을 차례로 클릭한 다음 아래로 스크롤하여 **System.Core**를 찾아 클릭하고 **확인**을 클릭합니다.  
  
5.  <xref:System.Linq>에 대한 `using` 지시문 또는 가져온 네임스페이스를 소스 코드 파일이나 프로젝트에 추가합니다.  
  
     자세한 내용은 [using 지시문](../Topic/using%20Directive%20\(C%23%20Reference\).md) 또는 [방법: 가져온 네임스페이스 추가 또는 제거\(Visual Basic\)](../Topic/How%20to:%20Add%20or%20Remove%20Imported%20Namespaces%20\(Visual%20Basic\).md)를 참조하세요.  
  
### LINQ to DataSet 기능을 사용하려면  
  
1.  필요한 경우 이 항목의 앞에서 설명한 단계에 따라 System.Core.dll에 대한 참조와 System.Linq에 대한 `using` 지시문 또는 가져온 네임스페이스를 추가합니다.  
  
2.  C\# 또는 Visual Basic에서 **프로젝트** 메뉴를 클릭한 다음 **참조 추가**를 클릭합니다.  
  
3.  **참조 추가** 대화 상자에서 **.NET** 탭이 맨 위에 있지 않으면 이 탭을 클릭합니다.  아래로 스크롤하여 **System.Data**와 **System.Data.DataSetExtensions**를 찾아서 클릭합니다.  **확인** 단추를 클릭합니다.  
  
4.  <xref:System.Data>에 대한 `using` 지시문 또는 가져온 네임스페이스를 소스 코드 파일이나 프로젝트에 추가합니다.  자세한 내용은 [using 지시문](../Topic/using%20Directive%20\(C%23%20Reference\).md) 또는 [방법: 가져온 네임스페이스 추가 또는 제거\(Visual Basic\)](../Topic/How%20to:%20Add%20or%20Remove%20Imported%20Namespaces%20\(Visual%20Basic\).md)를 참조하세요.  
  
5.  LINQ to Dataset 기능을 위해 System.Data.DataSetExtensions.dll에 대한 참조를 추가합니다.  System.Data.dll에 대한 참조가 아직 없으면 해당 참조를 추가합니다.  
  
6.  데이터베이스에 연결하는 방법에 따라 선택적으로 `System.Data.Common` 또는 `System.Data.SqlClient`에 대한 `using` 지시문 또는 가져온 네임스페이스를 추가합니다.  
  
## 참고 항목  
 [시작](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)   
 [Getting Started with LINQ](http://msdn.microsoft.com/ko-kr/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9)