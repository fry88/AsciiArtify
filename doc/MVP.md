# How to use argoCD or how to add app to argocd

## Prerequisites

- argoCD application is running
- enable port forwarding for access to app from your env (step 4 https://github.com/fry88/AsciiArtify/edit/main/doc/POC.md)

## setting new app in argoCD

1. Login to argoSD GUI with password from step 5 (https://github.com/fry88/AsciiArtify/edit/main/doc/POC.md)

   ```
   argoPass=$(kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d)
   echo $argoPass
   ```
  ![Screenshot 2023-05-28 at 20 28 44](https://github.com/fry88/AsciiArtify/assets/75542876/4645e9ce-0b16-494f-973b-28d73100cb9f)


2. Click to " + NEW APP" button in the upper left corner of the screen

<img width="1436" alt="Screenshot 2023-05-28 at 19 53 34" src="https://github.com/fry88/AsciiArtify/assets/75542876/2ee16473-d8d0-4012-90a5-59d1d80988fc">

3. In General section add Aplication Name (it can be whatever you want it to be)

4. In the drop-down list Project Name select deffault

5. In the source section -> Repository URL add you app repository URL

6. In DESTINATION section select the cluster and namespace where the application will be deployed

<img width="1436" alt="Screenshot 2023-05-28 at 19 54 26" src="https://github.com/fry88/AsciiArtify/assets/75542876/6810adc2-384b-4abc-a54e-20782d9cf397">

7. In SYNC OPTIONS it is important to choose AUTO-CREATE NAMESPACE

sync with github


https://github.com/fry88/AsciiArtify/assets/75542876/aac6a02a-598a-4678-8503-282fa7e9ff7d



