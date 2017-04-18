---
title: "방법: WCF REST 프로그래밍 모델을 사용하여 임의의 데이터를 허용하는 서비스 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e566c15a-b600-4e4a-be3a-4af43e767dae
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# 방법: WCF REST 프로그래밍 모델을 사용하여 임의의 데이터를 허용하는 서비스 만들기
서비스 작업에서 데이터가 반환되는 방법을 개발자가 완전히 제어해야 하는 경우가 있습니다. 서비스 작업이 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 지원되지 않는 형식으로 데이터를 반환해야 하는 경우가 그렇습니다. 이 항목에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] REST 프로그래밍 모델을 사용하여 임의의 데이터를 받는 서비스를 만드는 방법에 대해 설명합니다.  
  
### <a name="to-implement-the-service-contract"></a>서비스 계약을 구현하려면  
  
1.  서비스 계약을 정의합니다. 임의의 데이터를 수신 하는 작업의 형식 매개 변수가 있어야 합니다. <xref:System.IO.Stream>합니다. 또한 이 매개 변수는 요청 본문에서 전달된 유일한 매개 변수여야 합니다. 다음 예제에서 설명하는 작업은 파일 이름 매개 변수도 사용합니다. 이 매개 변수는 요청 URL 내에서 전달됩니다. 매개 변수를 지정 하 여 URL 내에서 전달 되도록 지정할 수는 <xref:System.UriTemplate> 에 <xref:System.ServiceModel.Web.WebInvokeAttribute>합니다. 이 경우 이 메서드를 호출하는 데 사용되는 URI는 “UploadFile/Some-Filename”으로 끝납니다. URI 템플릿의 “{filename}” 부분은 작업을 호출하는 데 사용되는 URI 내에서 작업에 대한 파일 이름 매개 변수가 전달되도록 지정합니다.  
  
    ```  
     [ServiceContract]  
    public interface IReceiveData  
    {  
        [WebInvoke(UriTemplate = "UploadFile/{fileName}")]  
        void UploadFile(string fileName, Stream fileContents);  
    }  
    ```  
  
2.  서비스 계약을 구현합니다. 계약에는 스트림의 임의의 데이터 파일을 받는 `UploadFile`메서드만 있습니다. 작업은 읽은 바이트 수를 계산하는 스트림을 읽고 나서 파일 이름과 읽은 바이트 수를 표시합니다.  
  
    ```  
    public class RawDataService : IReceiveData  
    {  
        public void UploadFile(string fileName, Stream fileContents)  
        {  
            byte[] buffer = new byte[10000];  
            int bytesRead, totalBytesRead = 0;  
            do  
            {  
                bytesRead = fileContents.Read(buffer, 0, buffer.Length);  
                totalBytesRead += bytesRead;  
            } while (bytesRead > 0);  
            Console.WriteLine("Service: Received file {0} with {1} bytes", fileName, totalBytesRead);  
        }  
    }  
    ```  
  
### <a name="to-host-the-service"></a>서비스를 호스트하려면  
  
1.  서비스를 호스트할 콘솔 응용 프로그램을 만듭니다.  
  
    ```  
    class Program  
    {  
       static void Main(string[] args)  
       {  
       }  
    }  
  
    ```  
  
2.  `Main` 메서드 내에 서비스의 기본 주소를 저장할 변수를 만듭니다.  
  
    ```  
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3.  만들기는 <xref:System.ServiceModel.ServiceHost> 서비스 클래스 및 기본 주소를 지정 하는 서비스에 대 한 인스턴스.  
  
    ```  
    ServiceHost host = new ServiceHost(typeof(RawDataService), new Uri(baseAddress));  
    ```  
  
4.  계약을 지정 하는 끝점 추가 <xref:System.ServiceModel.WebHttpBinding>, 및 <xref:System.ServiceModel.Description.WebHttpBehavior>합니다.  
  
    ```  
    host.AddServiceEndpoint(typeof(IReceiveData), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5.  서비스 호스트를 엽니다. 이제 서비스에서 요청을 받을 준비가 되었습니다.  
  
    ```  
    host.Open();  
    Console.WriteLine("Host opened");  
    ```  
  
### <a name="to-call-the-service-programmatically"></a>서비스를 프로그래밍 방식으로 호출하려면  
  
1.  만들기는 <xref:System.Net.HttpWebRequest> 서비스를 호출 하는 데 사용 하는 URI를 사용 합니다. 이 코드에서 기본 주소는 `“/UploadFile/Text”`와 결합됩니다. URI의 `“UploadFile”` 부분은 호출할 작업을 지정합니다. URI의 `“Test.txt”` 부분은 `UploadFile` 작업에 전달할 파일 이름 매개 변수를 지정합니다. 이러한 항목 모두 매핑되는 <xref:System.UriTemplate> 작업 계약에 적용 합니다.  
  
    ```  
    HttpWebRequest req = (HttpWebRequest)HttpWebRequest.Create(baseAddress + "/UploadFile/Test.txt");  
  
    ```  
  
2.  설정의 <xref:System.Net.HttpWebRequest.Method%2A> 의 속성은 <xref:System.Net.HttpWebRequest> 를 `POST` 및 <xref:System.Net.HttpWebRequest.ContentType%2A> 속성을 `“text/plain”`. 이렇게 하면 코드가 데이터를 보내고 있으며 데이터가 일반 텍스트 형식이라는 사실을 서비스에게 알립니다.  
  
    ```  
    req.Method = "POST";  
    req.ContentType = "text/plain";  
    ```  
  
3.  호출 <xref:System.Net.HttpWebRequest.GetRequestStream%2A> 하 여 요청 스트림을 가져오고, 데이터를 만들고 해당, 전송 및 해당 데이터를 요청 스트림에 쓰기 스트림을 닫습니다.  
  
    ```  
    Stream reqStream = req.GetRequestStream();  
    byte[] fileToSend = new byte[12345];  
    for (int i = 0; i < fileToSend.Length; i++)  
       {  
           fileToSend[i] = (byte)('a' + (i % 26));  
       }  
    reqStream.Write(fileToSend, 0, fileToSend.Length);  
    reqStream.Close();  
    ```  
  
4.  호출 하 여 서비스에서 요청을 가져오고 <xref:System.Net.HttpWebRequest.GetResponse%2A> 및 응답 데이터를 콘솔에 표시 합니다.  
  
    ```  
    HttpWebResponse resp = (HttpWebResponse)req.GetResponse();  
    Console.WriteLine("Client: Receive Response HTTP/{0} {1} {2}", resp.ProtocolVersion, (int)resp.StatusCode, resp.StatusDescription);  
  
    ```  
  
5.  서비스 호스트를 닫습니다.  
  
    ```  
    host.Close();  
    ```  
  
## <a name="example"></a>예제  
 다음은 이 예제에 해당되는 전체 코드 목록입니다.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.ServiceModel;  
using System.ServiceModel.Web;  
using System.ServiceModel.Description;  
using System.IO;  
using System.Net;  
  
namespace ReceiveRawData  
{  
    [ServiceContract]  
    public interface IReceiveData  
    {  
        [WebInvoke(UriTemplate = "UploadFile/{fileName}")]  
        void UploadFile(string fileName, Stream fileContents);  
    }  
    public class RawDataService : IReceiveData  
    {  
        public void UploadFile(string fileName, Stream fileContents)  
        {  
            byte[] buffer = new byte[10000];  
            int bytesRead, totalBytesRead = 0;  
            do  
            {  
                bytesRead = fileContents.Read(buffer, 0, buffer.Length);  
                totalBytesRead += bytesRead;  
            } while (bytesRead > 0);  
            Console.WriteLine("Service: Received file {0} with {1} bytes", fileName, totalBytesRead);  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
            ServiceHost host = new ServiceHost(typeof(RawDataService), new Uri(baseAddress));  
            host.AddServiceEndpoint(typeof(IReceiveData), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
            host.Open();  
            Console.WriteLine("Host opened");  
  
            HttpWebRequest req = (HttpWebRequest)HttpWebRequest.Create(baseAddress + "/UploadFile/Test.txt");  
            req.Method = "POST";  
            req.ContentType = "text/plain";  
            Stream reqStream = req.GetRequestStream();  
            byte[] fileToSend = new byte[12345];  
            for (int i = 0; i < fileToSend.Length; i++)  
            {  
                fileToSend[i] = (byte)('a' + (i % 26));  
            }  
            reqStream.Write(fileToSend, 0, fileToSend.Length);  
            reqStream.Close();  
            HttpWebResponse resp = (HttpWebResponse)req.GetResponse();  
            Console.WriteLine("Client: Receive Response HTTP/{0} {1} {2}", resp.ProtocolVersion, (int)resp.StatusCode, resp.StatusDescription);  
            host.Close();  
  
        }  
    }  
}  
  
```  
  
<!-- TODO: review snippet reference  [!CODE [Microsoft.Win32.RegistryKey#4](Microsoft.Win32.RegistryKey#4)]  -->  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
-   코드를 컴파일할 때 System.ServiceModel.dll 및 System.ServiceModel.Web.dll을 참조합니다.  
  
## <a name="see-also"></a>참고 항목  
 [UriTemplate 및 UriTemplateTable](../../../../docs/framework/wcf/feature-details/uritemplate-and-uritemplatetable.md)   
 [WCF 웹 HTTP 프로그래밍 모델](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)   
 [WCF 웹 HTTP 프로그래밍 모델 개요](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)