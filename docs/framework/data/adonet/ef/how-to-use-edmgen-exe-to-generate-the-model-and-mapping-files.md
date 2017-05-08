---
title: "방법: EdmGen.exe를 사용하여 모델 및 매핑 파일 생성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "ESQL"
  - "jsharp"
ms.assetid: 40db462d-2fd2-4cc1-ad86-d280403e63fa
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# 방법: EdmGen.exe를 사용하여 모델 및 매핑 파일 생성
이 항목에서는 EDM 생성기\(EdmGen.exe\) 도구를 사용하여 School 데이터베이스를 기반으로 하는 다음 파일을 생성하는 방법을 보여 줍니다.  
  
-   개념적 모델\(.csdl 파일\)  
  
-   저장소 모델\(.ssdl 파일\)  
  
-   개념적 모델과 저장소 모델 간의 매핑\(.msl 파일\)  
  
-   Visual Basic 또는 C\#의 개체 계층 코드  
  
-   뷰 파일  
  
 EdmGen.exe 도구에서는 \/mode:FullGeneration을 사용하여 위에 나열된 파일을 생성합니다.  EdmGen.exe 명령에 대한 자세한 내용은 [EDM 생성기\(EdmGen.exe\)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md)를 참조하세요.  
  
 EdmGen.exe를 사용하여 모델 및 매핑 파일을 생성할 경우에는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]를 사용하도록 [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] 프로젝트를 구성해야 합니다.  자세한 내용은 [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/ko-kr/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)을 참조하세요.  
  
> [!NOTE]
>  EdmGen.exe에서 생성된 개념적 모델에는 데이터베이스의 모든 개체가 포함됩니다.  특정 개체만 포함된 개념적 모델을 생성하려면 엔터티 데이터 모델 마법사를 사용합니다.  자세한 내용은 [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/ko-kr/dadb058a-c5d9-4c5c-8b01-28044112231d)을 참조하세요.  
  
### EdmGen.exe를 사용하여 Visual Basic 프로젝트용 School 모델을 생성하려면  
  
1.  School 데이터베이스를 만듭니다.  자세한 내용은 [Creating the School Sample Database](http://msdn.microsoft.com/ko-kr/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)을 참조하세요.  
  
2.  명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:VB  
  
    ```  
  
### EdmGen.exe를 사용하여 C\# 프로젝트용 School 모델을 생성하려면  
  
1.  School 데이터베이스를 만듭니다.  자세한 내용은 [Creating the School Sample Database](http://msdn.microsoft.com/ko-kr/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)을 참조하세요.  
  
2.  명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:CSharp  
    ```  
  
## 참고 항목  
 [모델링 및 매핑](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)   
 [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/ko-kr/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)   
 [How to: Pre\-Generate Views to Improve Query Performance](http://msdn.microsoft.com/ko-kr/b18a9d16-e10b-4043-ba91-b632f85a2579)   
 [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/ko-kr/91076853-0881-421b-837a-f582f36be527)   
 [방법: EdmGen.exe를 사용하여 모델 및 매핑 파일의 유효성 검사](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)