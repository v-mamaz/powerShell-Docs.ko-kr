---
title: 원격 runspace를 만드는 | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 057a666f-731b-423d-9d80-7be6b1836244
caps.latest.revision: 5
ms.openlocfilehash: f6cc69df8afe64cea867f5d7f9a7d45753a54d6f
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855809"
---
# <a name="creating-remote-runspaces"></a>원격 runspace 만들기

Windows PowerShell 명령을 사용 하는 한 `ComputerName` 매개 변수는 Windows PowerShell을 실행 하는 모든 컴퓨터에서 실행할 수 있습니다. 사용 하지 않는 명령을 실행 하는 `ComputerName` 매개 변수를 Ws-management를 사용 하 여 지정된 된 컴퓨터에 연결 하는 runspace를 구성 하는 컴퓨터에서 명령을 실행 합니다.

## <a name="using-a-wsmanconnection-to-create-a-remote-runspace"></a>WSManConnection를 사용 하 여 원격 runspace를 만드는

 원격 컴퓨터에 연결 하는 runspace를 만들려면, 한 [System.Management.Automation.Runspaces.Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo) 개체입니다. 설정 하 여 연결에 대 한 대상 끝점을 지정 합니다 [System.Management.Automation.Runspaces.Wsmanconnectioninfo.Connectionuri*](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo.ConnectionUri) 개체의 속성입니다. 다음 호출 하 여 runspace를 만들 합니다 [System.Management.Automation.Runspaces.Runspacefactory.Createrunspace*](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory.CreateRunspace) 메서드를 지정 하는 [System.Management.Automation.Runspaces.Wsmanconnectioninfo ](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo) 개체는 `connectionInfo` 매개 변수입니다.

 다음 예제에는 원격 컴퓨터에 연결 하는 runspace를 만드는 방법을 보여 줍니다. 예제에서는 `RemoteComputerUri` 원격 컴퓨터의 실제 URI에 대 한 자리 표시자로 사용 됩니다.

```csharp
namespace Samples
{
  using System;
  using System.Collections.ObjectModel;
  using System.Management.Automation;            // Windows PowerShell namespace.
  using System.Management.Automation.Runspaces;  // Windows PowerShell namespace.

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class RemoteRunspace02
  {
    /// <summary>
    /// This sample shows how to create a remote runspace that
    /// runs commands on the local computer.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    private static void Main(string[] args)
    {
      // Create a WSManConnectionInfo object using the default constructor
      // to connect to the "localHost". The WSManConnectionInfo object can
      // also be used to specify connections to remote computers.
      WSManConnectionInfo connectionInfo = new WSManConnectionInfo();

      // Set the OperationTimeout property and OpenTimeout properties.
      // The OperationTimeout property is used to tell Windows PowerShell
      // how long to wait (in milliseconds) before timing out for an
      // operation. The OpenTimeout property is used to tell Windows
      // PowerShell how long to wait (in milliseconds) before timing out
      // while establishing a remote connection.
      connectionInfo.OperationTimeout = 4 * 60 * 1000; // 4 minutes.
      connectionInfo.OpenTimeout = 1 * 60 * 1000; // 1 minute.

      // Create a remote runspace using the connection information.
      //using (Runspace remoteRunspace = RunspaceFactory.CreateRunspace())
      using (Runspace remoteRunspace = RunspaceFactory.CreateRunspace(connectionInfo))
      {
        // Establish the connection by calling the Open() method to open the runspace.
        // The OpenTimeout value set previously will be applied while establishing
        // the connection. Establishing a remote connection involves sending and
        // receiving some data, so the OperationTimeout will also play a role in this process.
          remoteRunspace.Open();

        // Create a PowerShell object to run commands in the remote runspace.
        using (PowerShell powershell = PowerShell.Create())
        {
          powershell.Runspace = remoteRunspace;
          powershell.AddCommand("get-process");
          powershell.Invoke();

          Collection<PSObject> results = powershell.Invoke();

          Console.WriteLine("Process              HandleCount");
          Console.WriteLine("--------------------------------");

          // Display the results.
          foreach (PSObject result in results)
          {
            Console.WriteLine(
                              "{0,-20} {1}",
                              result.Members["ProcessName"].Value,
                              result.Members["HandleCount"].Value);
          }
        }

        // Close the connection. Call the Close() method to close the remote
        // runspace. The Dispose() method (called by using primitive) will call
        // the Close() method if it is not already called.
        remoteRunspace.Close();
      }
    }
  }
}
```
