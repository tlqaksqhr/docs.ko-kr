---
title: "방법: EdmGen.exe를 사용하여 개체 계층 코드 생성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: dd5c8f578e6e3f0816dff06909a44d80a1c0fd57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a>방법: EdmGen.exe를 사용하여 개체 계층 코드 생성
이 항목에서는 사용 하 여 [EDM 생성기 (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) .csdl 파일을 기반으로 하는 개체 계층 코드를 생성 하는 도구입니다.  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>EdmGen.exe를 사용하여 Visual Basic 프로젝트용 School 모델의 개체 계층 코드를 생성하려면  
  
1.  School 데이터베이스를 만듭니다. 자세한 내용은 참조 [School 샘플 데이터베이스 만들기](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)합니다.  
  
2.  School 모델을 생성하거나 School.csdl 파일을 가져옵니다. 자세한 내용은 참조 [하는 방법: 모델 및 매핑 파일 생성을 사용 하 여 EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)합니다.  
  
3.  명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a>EdmGen.exe를 사용하여 C# 프로젝트용 School 모델의 개체 계층 코드를 생성하려면  
  
1.  School 데이터베이스를 만듭니다. 자세한 내용은 참조 [School 샘플 데이터베이스 만들기](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)합니다.  
  
2.  School 모델을 생성하거나 School.csdl 파일을 가져옵니다. 자세한 내용은 참조 [하는 방법: 모델 및 매핑 파일 생성을 사용 하 여 EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)합니다.  
  
3.  명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [모델링 및 매핑](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [방법: 수동으로 Entity Framework 프로젝트 구성](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [ADO.NET 엔터티 데이터 모델 도구](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)  
 [방법: 쿼리 성능을 개선 하는 뷰를 미리 생성](http://msdn.microsoft.com/en-us/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [방법: EdmGen.exe를 사용하여 모델 생성 및 파일 매핑](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
