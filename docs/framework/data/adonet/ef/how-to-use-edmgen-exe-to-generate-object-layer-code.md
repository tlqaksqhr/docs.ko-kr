---
title: "방법: EdmGen.exe를 사용하여 개체 계층 코드 생성 | Microsoft Docs"
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
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# 방법: EdmGen.exe를 사용하여 개체 계층 코드 생성
이 항목에서는 [EDM 생성기\(EdmGen.exe\)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) 도구를 사용하여 .csdl 파일을 기반으로 개체 계층 코드를 생성하는 방법을 보여 줍니다.  
  
### EdmGen.exe를 사용하여 Visual Basic 프로젝트용 School 모델의 개체 계층 코드를 생성하려면  
  
1.  School 데이터베이스를 만듭니다.  자세한 내용은 [Creating the School Sample Database](http://msdn.microsoft.com/ko-kr/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)을 참조하세요.  
  
2.  School 모델을 생성하거나 School.csdl 파일을 가져옵니다.  자세한 내용은 [방법: EdmGen.exe를 사용하여 모델 및 매핑 파일 생성](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)을 참조하세요.  
  
3.  명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### EdmGen.exe를 사용하여 C\# 프로젝트용 School 모델의 개체 계층 코드를 생성하려면  
  
1.  School 데이터베이스를 만듭니다.  자세한 내용은 [Creating the School Sample Database](http://msdn.microsoft.com/ko-kr/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)을 참조하세요.  
  
2.  School 모델을 생성하거나 School.csdl 파일을 가져옵니다.  자세한 내용은 [방법: EdmGen.exe를 사용하여 모델 및 매핑 파일 생성](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)을 참조하세요.  
  
3.  명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## 참고 항목  
 [모델링 및 매핑](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)   
 [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/ko-kr/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)   
 [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/ko-kr/91076853-0881-421b-837a-f582f36be527)   
 [How to: Pre\-Generate Views to Improve Query Performance](http://msdn.microsoft.com/ko-kr/b18a9d16-e10b-4043-ba91-b632f85a2579)   
 [방법: EdmGen.exe를 사용하여 모델 및 매핑 파일 생성](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)