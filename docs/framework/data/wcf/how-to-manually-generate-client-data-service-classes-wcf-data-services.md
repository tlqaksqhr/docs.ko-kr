---
title: "방법: 수동으로 클라이언트 데이터 서비스 클래스 생성(WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dba117ac9f4fd7dc745019d9705c2a707a5b526c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a>방법: 수동으로 클라이언트 데이터 서비스 클래스 생성(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]사용 하는 경우 클라이언트 데이터 서비스 클래스를 자동으로 생성할 수 있도록 Visual Studio와 통합 하는 **서비스 참조 추가** 대화 상자는 Visual Studio 프로젝트에는 데이터 서비스에 대 한 참조를 추가할 수 있습니다. 자세한 내용은 참조 [하는 방법: 데이터 서비스 참조 추가](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)합니다. 코드 생성 도구 `DataSvcUtil.exe`를 사용하여 동일한 클라이언트 데이터 서비스 클래스를 수동으로 생성할 수도 있습니다. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에 포함된 이 도구는 데이터 서비스 정의에서 .NET Framework 클래스를 생성합니다. 이 도구를 사용하여 개념적 모델 파일(.csdl) 및 Visual Studio 프로젝트의 Entity Framework 모델을 나타내는 .edmx 파일에서 데이터 서비스 클래스를 생성할 수도 있습니다.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스를 기반으로 하여 클라이언트 데이터 서비스 클래스를 만듭니다. 이 서비스를 완료할 때 만드는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다. 이 항목의 일부 예제에는 Northwind 모델에 대한 개념적 모델 파일이 필요합니다. 자세한 내용은 참조 [하는 방법: 모델 및 매핑 파일 생성을 사용 하 여 EdmGen.exe](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)합니다. 이 항목의 일부 예제에는 Northwind 모델에 대한 .edmx 파일이 필요합니다. 자세한 내용은 참조 [.edmx 파일 개요](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)합니다.  
  
### <a name="to-generate-c-classes-that-support-data-binding"></a>데이터 바인딩을 지원하는 C# 클래스를 생성하려면  
  
-   명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  `/uri:` 매개 변수에 제공된 값을 Northwind 샘플 데이터 서비스 인스턴스의 URI로 바꾸어야 합니다.  
  
### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a>데이터 바인딩을 지원하는 Visual Basic 클래스를 생성하려면  
  
-   명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  `/uri:` 매개 변수에 제공된 값을 Northwind 샘플 데이터 서비스 인스턴스의 URI로 바꾸어야 합니다.  
  
### <a name="to-generate-c-classes-based-on-the-service-uri"></a>서비스 URI를 기반으로 하여 C# 클래스를 생성하려면  
  
-   명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  `/uri:` 매개 변수에 제공된 값을 Northwind 샘플 데이터 서비스 인스턴스의 URI로 바꾸어야 합니다.  
  
### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a>서비스 URI를 기반으로 하여 Visual Basic 클래스를 생성하려면  
  
-   명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  `/uri:` 매개 변수에 제공된 값을 Northwind 샘플 데이터 서비스 인스턴스의 URI로 바꾸어야 합니다.  
  
### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a>개념적 모델 파일(CSDL)을 기반으로 하여 C# 클래스를 생성하려면  
  
-   명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs  
    ```  
  
### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a>개념적 모델 파일(CSDL)을 기반으로 하여 Visual Basic 클래스를 생성하려면  
  
-   명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb  
    ```  
  
### <a name="to-generate-c-classes-based-on-the-edmx-file"></a>.edmx 파일을 기반으로 하여 C# 클래스를 생성하려면  
  
-   명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs   
    ```  
  
### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a>.edmx 파일을 기반으로 하여 Visual Basic 클래스를 생성하려면  
  
-   명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb   
    ```  
  
## <a name="see-also"></a>참고 항목  
 [데이터 서비스 클라이언트 라이브러리 생성](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
 [방법: 데이터 서비스 참조 추가](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)  
 [WCF Data Services 클라이언트 유틸리티(DataSvcUtil.exe)](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)
