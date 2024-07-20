# Assignment-6



# Azure Storage 

## Table of Contents
1. [Create a Storage Account](#create-a-storage-account)
2. [Upload and Access Blob](#upload-and-access-blob)
3. [Explore Different Authentication Techniques](#explore-different-authentication-techniques)
4. [Use Azure Storage Explorer](#use-azure-storage-explorer)
5. [Provision Access Keys](#provision-access-keys)
6. [Create a Shared Access Signature (SAS)](#create-a-shared-access-signature-sas)
7. [Create a Stored Access Policy](#create-a-stored-access-policy)
8. [Learn About Access Tiers](#learn-about-access-tiers)
9. [Apply Lifecycle Policy](#apply-lifecycle-policy)
10. [Test Object Replication in Blob](#test-object-replication-in-blob)
11. [Create a File Share](#create-a-file-share)
12. [Create Azure File Sync](#create-azure-file-sync)

---

## 1. Create a Storage Account

**Step-by-Step Guide:**

1. **Sign in to Azure Portal:**
   - Open [Azure Portal](https://portal.azure.com) and sign in with your Azure account.

2. **Create a Storage Account:**
   - In the Azure Portal, select `Create a resource`.
   - Search for `Storage account` and select it from the list.
   - Click `Create` to start the creation process.

3. **Configure the Storage Account:**
   - **Basics Tab:**
     - **Subscription:** Select your Azure subscription.
     - **Resource Group:** Create a new resource group or select an existing one.
     - **Storage Account Name:** Enter a unique name for your storage account.
     - **Region:** Choose a region closest to your users.
     - **Performance:** Select `Standard` or `Premium` based on your needs.
     - **Replication:** Choose a replication strategy (LRS, GRS, RA-GRS, ZRS).

   - **Advanced Tab:**
     - **Secure Transfer Required:** Enable or disable secure transfer.
     - **Large File Shares:** Enable if you need large file shares (optional).
     - **Blob Soft Delete:** Enable to recover deleted blobs (optional).

   - **Networking Tab:**
     - **Connectivity Method:** Choose between `Public endpoint (all networks)`, `Public endpoint (selected networks)`, or `Private endpoint`.
     - **Firewall and Virtual Networks:** Configure network access rules if needed.

   - **Data Protection Tab:**
     - **Blob Soft Delete:** Enable or disable.
     - **Container Soft Delete:** Enable or disable.
     - **Versioning:** Enable or disable blob versioning.

   - **Tags Tab:**
     - Add tags to organize your resources (optional).

   - **Review + Create Tab:**
     - Review your settings and click `Create`.

4. **Wait for Deployment:**
   - Once the deployment is complete, go to the newly created storage account.

---

## 2. Upload and Access Blob

**Step-by-Step Guide:**

1. **Navigate to the Storage Account:**
   - In the Azure Portal, go to your storage account.

2. **Create a Container:**
   - Under `Data storage`, select `Containers`.
   - Click `+ Container` to create a new container.
   - Enter a name for the container and set the access level (Private, Blob, Container).

3. **Upload a Blob:**
   - Open the container you created.
   - Click `Upload` and select the file you want to upload.
   - Click `Upload` to start the process.

4. **Access the Blob:**
   - Once uploaded, you can see the blob in the container.
   - Click on the blob to get its URL and access it.

---

## 3. Explore Different Authentication Techniques

**Authentication Techniques:**

1. **Azure Active Directory (AAD):**
   - Secure method using Azure AD credentials.
   - Use Azure AD to grant access to resources in your storage account.

2. **Shared Key (Account Key):**
   - Use the storage account name and account key to access resources.

3. **Shared Access Signatures (SAS):**
   - Generate SAS tokens to delegate access with specified permissions and timeframes.

4. **Azure Storage Explorer:**
   - A tool to manage storage accounts and access data.

---

## 4. Use Azure Storage Explorer

**Step-by-Step Guide:**

1. **Download and Install:**
   - Download [Azure Storage Explorer](https://azure.microsoft.com/en-us/features/storage-explorer/).
   - Install it on your machine.

2. **Connect to Storage Account:**
   - Open Azure Storage Explorer.
   - Click `Add an Account`.
   - Choose the connection method (Azure AD, account name and key, SAS).

3. **Manage Data:**
   - Use the explorer to upload, download, and manage blobs, files, queues, and tables.

---

## 5. Provision Access Keys

**Step-by-Step Guide:**

1. **Access Keys:**
   - In the Azure Portal, navigate to your storage account.
   - Under `Security + networking`, select `Access keys`.
   - You will see two keys (key1 and key2) and connection strings.

2. **Use Access Keys:**
   - Copy the key and use it to connect to your storage account via applications or Azure Storage Explorer.

---

## 6. Create a Shared Access Signature (SAS)

**Step-by-Step Guide:**

1. **Generate SAS:**
   - In the Azure Portal, navigate to your storage account.
   - Under `Security + networking`, select `Shared access signature`.
   - Configure the SAS settings (permissions, start and expiry date/time).
   - Click `Generate SAS token and URL`.

2. **Check Access Scope:**
   - Use the generated SAS token to access resources within the defined scope.

---

## 7. Create a Stored Access Policy

**Step-by-Step Guide:**

1. **Create Stored Access Policy:**
   - In the Azure Portal, navigate to your container.
   - Under `Settings`, select `Access policy`.
   - Click `+ Add policy` to create a new policy.
   - Set the permissions and expiry date.

2. **Associate SAS with Policy:**
   - Generate a SAS and associate it with the stored access policy.
   - Test access to verify the policy's scope.

---

## 8. Learn About Access Tiers

**Access Tiers:**

1. **Hot:**
   - For data that is accessed frequently.
   - Higher storage cost, lower access cost.

2. **Cool:**
   - For data that is infrequently accessed.
   - Lower storage cost, higher access cost.

3. **Archive:**
   - For data that is rarely accessed and has long-term retention.
   - Lowest storage cost, highest access cost (requires rehydration).

---

## 9. Apply Lifecycle Policy

**Step-by-Step Guide:**

1. **Create Lifecycle Policy:**
   - In the Azure Portal, navigate to your storage account.
   - Under `Data management`, select `Lifecycle management`.
   - Click `+ Add rule` to create a new policy.
   - Define conditions and actions (e.g., move to cool storage after 30 days).

2. **Test the Policy:**
   - Upload data and monitor its transition through different access tiers based on the policy.

---

## 10. Test Object Replication in Blob

**Step-by-Step Guide:**

1. **Enable Replication:**
   - In the Azure Portal, navigate to your storage account.
   - Under `Data management`, select `Object replication`.
   - Configure replication rules and pair source and destination accounts.

2. **Verify Replication:**
   - Upload data to the source account and verify its replication to the destination account.

---

## 11. Create a File Share

**Step-by-Step Guide:**

1. **Create File Share:**
   - In the Azure Portal, navigate to your storage account.
   - Under `Data storage`, select `File shares`.
   - Click `+ File share` to create a new file share.
   - Enter a name and set the quota.

2. **Test Functionality:**
   - Use Azure Storage Explorer or SMB to access and manage the file share.

---

## 12. Create Azure File Sync

**Step-by-Step Guide:**

1. **Install Azure File Sync Agent:**
   - Download and install the [Azure File Sync agent](https://docs.microsoft.com/en-us/azure/storage/files/storage-sync-files-server-install-agent) on your Windows Server.

2. **Register Server:**
   - Register your Windows Server with your Storage Sync Service.

3. **Create Sync Group:**
   - In the Azure Portal, navigate to your Storage Sync Service.
   - Create a new sync group and add the file share and registered server endpoint.

4. **Configure Sync:**
   - Configure the sync settings and start syncing files between the file share and your server.

---

