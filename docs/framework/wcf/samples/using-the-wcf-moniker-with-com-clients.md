---
title: Using the WCF Moniker with COM Clients
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2799bfe-88bd-49d7-9d6d-ac16a9b16b04
caps.latest.revision: 34
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 322467510d499040c07d6e5e84842542aa325737
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="using-the-wcf-moniker-with-com-clients"></a>Using the WCF Moniker with COM Clients
이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스 모니커를 사용하여 웹 서비스를 Microsoft Office VBA(Office Visual Basic for Applications) 또는 Visual Basic 6.0과 같은 COM 기반 개발 환경에 통합하는 방법을 보여 줍니다. 이 샘플은 IIS(인터넷 정보 서비스)에서 호스트되는 Windows 스크립트 호스트 클라이언트(.vbs), 지원 클라이언트 라이브러리(.dll) 및 서비스 라이브러리(.dll)로 구성됩니다. 서비스는 계산기 서비스이고 COM 클라이언트는 서비스에서 수학 작업인 Add, Subtract, Multiply 및 Divide를 호출합니다. 클라이언트 동작이 메시지 상자 창에 표시됩니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\COM`  
  
 서비스는 다음 코드 예제와 같이 정의된 `ICalculator` 계약을 구현합니다.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 이 샘플에서는 모니커 사용을 위한 세 가지 대체 방법을 보여 줍니다.  
  
-   형식화된 계약 – 계약이 클라이언트 컴퓨터에 COM 노출 형식으로 등록됩니다.  
  
-   WSDL 계약 – 계약이 WSDL 문서 형식으로 제공됩니다.  
  
-   메타데이터 교환 계약 - 계약이 MEX(메타데이터 교환) 끝점에서 런타임에 검색됩니다.  
  
## <a name="typed-contract"></a>형식화된 계약  
 형식화된 계약 사용과 함께 모니커를 사용하려면 서비스 계약에 대한 적절한 특성 사용 형식을 COM에 등록해야 합니다. 먼저, 클라이언트를 사용 하 여 생성 해야 합니다는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다. 클라이언트 디렉터리의 명령 프롬프트에서 다음 명령을 실행하여 형식화된 프록시를 생성합니다.  
  
```  
svcutil.exe /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost/servicemodelsamples/service.svc /out:generatedClient.cs  
```  
  
 이 클래스는 프로젝트에 포함되어야 하고 프로젝트는 컴파일 시에 서명된 COM 노출 어셈블리를 생성하도록 구성되어야 합니다. 다음 특성이 AssemblyInfo.cs 파일에 포함되어야 합니다.  
  
```  
[assembly: ComVisible(true)]  
```  
  
 프로젝트를 빌드한 후 다음 예제와 같이 `regasm`을 사용하여 COM 노출 형식을 등록합니다.  
  
```  
regasm.exe /tlb:CalcProxy.tlb client.dll  
```  
  
 만들어진 어셈블리는 전역 어셈블리 캐시에 추가되어야 합니다. 반드시 필요한 것은 아니지만 이렇게 하면 어셈블리를 찾는 런타임 프로세스가 단순화됩니다. 다음 명령은 전역 어셈블리 캐시에 어셈블리를 추가합니다.  
  
```  
gacutil.exe /i client.dll  
```  
  
> [!NOTE]
>  서비스 모니커에는 형식 등록만 필요하고 서비스와 통신하기 위해 프록시가 사용되지 않습니다.  
  
 ComCalcClient.vbs 클라이언트 응용 프로그램은 `GetObject` 함수를 사용하여 서비스용 프록시를 생성하며 서비스에 대한 주소, 바인딩 및 계약을 지정하기 위해 서비스 모니커 구문이 사용됩니다.  
  
```  
Set typedServiceMoniker = GetObject(  
"service4:address=http://localhost/ServiceModelSamples/service.svc, binding=wsHttpBinding,   
contractType={9213C6D2-5A6F-3D26-839B-3BA9B82228D3}")  
```  
  
 모니커에 사용되는 매개 변수는 다음을 지정합니다.  
  
-   서비스 끝점의 주소입니다.  
  
-   해당 끝점과 연결하기 위해 클라이언트가 사용해야 하는 바인딩. 이 경우 클라이언트 구성 파일에 사용자 지정 바인딩이 정의될 수도 있지만 시스템 정의 wsHttpBinding이 사용됩니다. Windows 스크립트 호스트와 함께 사용하는 경우 사용자 지정 바인딩은 Cscript.exe와 동일한 디렉터리의 Cscript.exe.config 파일에 정의됩니다.  
  
-   끝점에서 지원되는 계약의 형식. 이는 위에서 생성 및 등록된 형식입니다. Visual Basic 스크립트에서 강력한 형식의 COM 환경이 제공되지 않으므로 계약에 대한 식별자를 지정해야 합니다. 이 GUID는 OLE/COM 개체 뷰어(OleView.exe)와 같은 COM 도구를 사용하여 볼 수 있는 CalcProxy.tlb에 있는 `interfaceID`입니다. Office VBA 또는 Visual Basic 6.0과 같은 강력한 형식의 환경인 경우 계약 매개 변수 대신에 형식 라이브러리에 명시적 참조를 추가한 다음 프록시 개체의 형식을 선언하는 방법을 사용할 수 있습니다. 또한 이렇게 하면 클라이언트 응용 프로그램 개발 도중에 IntelliSense 지원이 제공됩니다.  
  
 서비스 모니커를 사용하여 프록시 인스턴스를 생성한 후 클라이언트 응용 프로그램은 프록시에서 메서드를 호출할 수 있습니다. 이렇게 하면 결과적으로 서비스 모니커 인프라에서 해당 서비스 작업을 호출하게 됩니다.  
  
```  
' Call the service operations using the moniker object  
WScript.Echo "Typed service moniker: 100 + 15.99 = " & typedServiceMoniker.Add(100, 15.99)  
```  
  
 샘플을 실행할 경우 작업 응답이 Windows 스크립트 호스트 메시지 상자 창에 표시됩니다. 이 응답은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스와 통신하기 위해 형식화된 모니커를 사용하여 COM 호출을 수행하는 COM 클라이언트를 보여 줍니다. 클라이언트 응용 프로그램에서 COM이 사용되지만 서비스와의 통신은 웹 서비스 호출로만 구성됩니다.  
  
## <a name="wsdl-contract"></a>WSDL 계약  
 WSDL 계약과 함께 모니커를 사용하려면 클라이언트 라이브러리 등록이 필요하지 않지만 브라우저를 사용하여 서비스의 WSDL 끝점에 액세스하는 것처럼 out-of-band 메커니즘을 통해 서비스에 대한 WSDL 계약을 검색해야 합니다. 그런 다음 모니커는 실행 시에 해당 계약에 액세스할 수 있습니다.  
  
 ComCalcClient.vbs 클라이언트 응용 프로그램은 `FileSystemObject`를 사용하여 로컬로 저장된 WSDL 파일에 액세스한 다음 `GetObject` 함수를 다시 사용하여 서비스에 대한 프록시를 생성합니다.  
  
```  
' Open the WSDL contract file and read it all into the wsdlContract string  
Const ForReading = 1  
Set objFSO = CreateObject("Scripting.FileSystemObject")  
Set objFile = objFSO.OpenTextFile("serviceWsdl.xml", ForReading)  
wsdlContract = objFile.ReadAll  
objFile.Close  
  
' Create a string for the service moniker including the content of the WSDL contract file  
wsdlMonikerString = "service4:address='http://localhost/ServiceModelSamples/service.svc'"  
wsdlMonikerString = wsdlMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
wsdlMonikerString = wsdlMonikerString + ", wsdl='" & wsdlContract & "'"  
wsdlMonikerString = wsdlMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
' Create the service moniker object  
Set wsdlServiceMoniker = GetObject(wsdlMonikerString)  
```  
  
 모니커에 사용되는 매개 변수는 다음을 지정합니다.  
  
-   서비스 끝점의 주소입니다.  
  
-   해당 끝점과 연결하기 위해 클라이언트가 사용해야 하는 바인딩 및 해당 바인딩이 정의되는 네임스페이스. 이 경우 `wsHttpBinding_ICalculator`가 사용됩니다.  
  
-   계약을 정의하는 WSDL. 이 경우 serviceWsdl.xml 파일에서 읽은 문자열입니다.  
  
-   계약의 이름 및 네임스페이스. WSDL에 둘 이상의 계약이 포함될 수도 있으므로 이 식별 정보가 필요합니다.  
  
    > [!NOTE]
    >  기본적으로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 사용되는 각 네임스페이스에 대해 별개의 WSDL 파일을 생성합니다. 이러한 파일은 WSDL 가져오기 구문 사용과 연결됩니다. 모니커에 단일 WSDL 정의가 필요하므로 이 샘플에 표시된 것처럼 단일 네임스페이스가 서비스에 사용되거나 별개의 파일을 수동으로 병합해야 합니다.  
  
 서비스 모니커를 사용하여 프록시 인스턴스를 생성한 후 클라이언트 응용 프로그램은 프록시에서 메서드를 호출할 수 있습니다. 이렇게 하면 결과적으로 서비스 모니커 인프라에서 해당 서비스 작업을 호출하게 됩니다.  
  
```  
' Call the service operations using the moniker object  
WScript.Echo "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
```  
  
 샘플을 실행할 경우 작업 응답이 Windows 스크립트 호스트 메시지 상자 창에 표시됩니다. 이 응답은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스와 통신하기 위해 WSDL 계약과 함께 모니커를 사용하여 COM 호출을 수행하는 COM 클라이언트를 보여 줍니다.  
  
## <a name="metadata-exchange-contract"></a>메타데이터 교환 계약  
 MEX 계약과 함께 모니커를 사용하려면 WSDL 계약과 마찬가지로 클라이언트 등록이 필요하지 않습니다. 서비스에 대한 계약은 메타데이터 교환의 내부 사용을 통해 실행 시에 검색됩니다.  
  
 ComCalcClient.vbs 클라이언트 응용 프로그램은 `GetObject` 함수를 다시 사용하여 서비스에 대한 프록시를 생성합니다.  
  
```  
' Create a string for the service moniker specifying the address to retrieve the service metadata from  
mexMonikerString = "service4:mexAddress='http://localhost/servicemodelsamples/service.svc/mex'"  
mexMonikerString = mexMonikerString + ", address='http://localhost/ServiceModelSamples/service.svc'"  
mexMonikerString = mexMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
mexMonikerString = mexMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
' Create the service moniker object  
Set mexServiceMoniker = GetObject(mexMonikerString)  
```  
  
 모니커에 사용되는 매개 변수는 다음을 지정합니다.  
  
-   서비스 메타데이터 교환 끝점의 주소  
  
-   서비스 끝점의 주소입니다.  
  
-   해당 끝점과 연결하기 위해 클라이언트가 사용해야 하는 바인딩 및 해당 바인딩이 정의되는 네임스페이스. 이 경우 `wsHttpBinding_ICalculator`가 사용됩니다.  
  
-   계약의 이름 및 네임스페이스. WSDL에 둘 이상의 계약이 포함될 수도 있으므로 이 식별 정보가 필요합니다.  
  
 서비스 모니커를 사용하여 프록시 인스턴스를 생성한 후 클라이언트 응용 프로그램은 프록시에서 메서드를 호출할 수 있습니다. 이렇게 하면 결과적으로 서비스 모니커 인프라에서 해당 서비스 작업을 호출하게 됩니다.  
  
```  
' Call the service operations using the moniker object  
WScript.Echo "MEX service moniker: 9 * 81.25 = " & mexServiceMoniker.Multiply(9, 81.25)  
```  
  
 샘플을 실행할 경우 작업 응답이 Windows 스크립트 호스트 메시지 상자 창에 표시됩니다. 이 응답은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스와 통신하기 위해 MEX 계약과 함께 모니커를 사용하여 COM 호출을 수행하는 COM 클라이언트를 보여 줍니다.  
  
#### <a name="to-set-up-and-build-the-sample"></a>샘플을 설치하고 빌드하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  Visual Studio 명령 프롬프트에서 언어별 폴더의 \client\bin 폴더를 엽니다.  
  
    > [!NOTE]
    >  [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], Windows 7 또는 Windows Server 2008 R2를 사용하는 경우에는 관리자 권한으로 명령 프롬프트를 실행해야 합니다.  
  
4.  에 입력 `tlbexp.exe client.dll /out:CalcProxy.tlb` 하 여 dll을 tlb 파일로 내보냅니다. "형식 라이브러리 내보내기 경고"가 발생할 수 있지만 제네릭 형식이 필요하지 않으므로 문제가 되지는 않습니다.  
  
5.  에 입력 `regasm.exe /tlb:CalcProxy.tlb client.dll` 형식을 COM에 등록 하려면 "형식 라이브러리 내보내기 경고"가 발생할 수 있지만 제네릭 형식이 필요하지 않으므로 문제가 되지는 않습니다.  
  
6.  에 입력 `gacutil.exe /i client.dll` 를 전역 어셈블리 캐시에 어셈블리를 추가 합니다.  
  
#### <a name="to-run-the-sample-on-the-same-computer"></a>단일 컴퓨터 구성에서 샘플을 실행하려면  
  
1.  다음 주소에 입력 하 여 브라우저를 사용 하는 서비스에 액세스할 수 있는 테스트: `http://localhost/servicemodelsamples/service.svc`합니다. 확인 페이지가 응답으로 표시됩니다.  
  
2.  언어별 폴더의 \client에서 ComCalcClient.vbs를 실행합니다. 메시지 상자 창에 클라이언트 동작이 표시됩니다.  
  
3.  클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.  
  
#### <a name="to-run-the-sample-across-computers"></a>다중 컴퓨터 구성에서 샘플을 실행하려면  
  
1.  서비스 컴퓨터에서 ServiceModelSamples라는 가상 디렉터리를 만듭니다. 샘플에 포함된 Setupvroot.bat 스크립트를 사용하여 디스크 디렉터리와 가상 디렉터리를 만들 수 있습니다  
  
2.  %SystemDrive%\Inetpub\wwwroot\servicemodelsamples에서 서비스 프로그램 파일을 서비스 컴퓨터의 ServiceModelSamples 가상 디렉터리로 복사합니다. \bin 디렉터리에 파일을 포함해야 합니다.  
  
3.  언어별 폴더의 \client 폴더에서 클라이언트 컴퓨터로 클라이언트 스크립트 파일을 복사합니다.  
  
4.  스크립트 파일에서 끝점 정의의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다. 주소에서 "localhost"에 대한 참조를 정규화된 도메인 이름으로 바꿉니다.  
  
5.  WSDL 파일을 클라이언트 컴퓨터로 복사합니다. WSDL 파일 serviceWsdl.xml에서 주소의 "localhost"에 대한 참조를 정규화된 도메인 이름으로 바꿉니다.  
  
6.  언어별 폴더의 \client\bin 폴더에서 클라이언트 컴퓨터의 디렉터리로 Client.dll 라이브러리를 복사합니다.  
  
7.  명령 프롬프트에서 클라이언트 컴퓨터의 대상 디렉터리로 이동합니다. [!INCLUDE[wv](../../../../includes/wv-md.md)] 또는 [!INCLUDE[lserver](../../../../includes/lserver-md.md)]을 사용할 경우 관리자 권한으로 명령 프롬프트를 실행해야 합니다.  
  
8.  에 입력 `tlbexp.exe client.dll /out:CalcProxy.tlb` 하 여 dll을 tlb 파일로 내보냅니다. "형식 라이브러리 내보내기 경고"가 발생할 수 있지만 제네릭 형식이 필요하지 않으므로 문제가 되지는 않습니다.  
  
9. 에 입력 `regasm.exe /tlb:CalcProxy.tlb client.dll` 형식을 COM에 등록 하려면 가 포함 된 폴더로 경로가 설정 되었는지 확인 하십시오. `regasm.exe` 명령을 실행 하기 전에.  
  
10. 에 입력 `gacutil.exe /i client.dll` 를 전역 어셈블리 캐시에 어셈블리를 추가 합니다. 가 포함 된 폴더로 경로가 설정 되었는지 확인 하십시오. `gacutil.exe` 명령을 실행 하기 전에.  
  
11. 클라이언트 컴퓨터에서 브라우저를 사용하여 서비스에 액세스할 수 있는지 테스트합니다.  
  
12. 클라이언트 컴퓨터에서 ComCalcClient.vbs를 실행합니다.  
  
#### <a name="to-clean-up-after-the-sample"></a>샘플 실행 후 정리를 수행하려면  
  
-   보안을 위해 샘플 사용이 끝나면 설정 단계에서 부여된 가상 디렉터리 정의와 사용 권한을 제거합니다.  
  
## <a name="see-also"></a>참고 항목
