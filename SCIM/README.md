![Axiad logo](images/axiad_logo.png)

# Axiad

Axiad enables customers to move to a passwordless future without the friction and risk of fragmented solutions. By addressing authentication holistically, regardless of underlying IT complexity, organizations can vastly improve their cybersecurity posture.

Please refer to our website for more information about [Axiad](https://www.axiad.com/).

## Axiad SCIM Connector

Axiad SCIM Connector enable automatic provisioning of users and groups between Axiad Cloud and ForgeRock using secure and standard protocol, System for Cross-Domain Identity Managemen(SCIM). Axiad SCIM connector allows partners to levarge Certificate Based Authentication, which is the most secure, phishing-resistant forms of multi-factor authentication (MFA) and is increasingly deployed in enterprises and the public sector. Many enterprise employees, as well as the majority of federal agency and defense employees/contractors, use a strong authenticator such as a smart card or hardware device for authentication. CBA streamlines the process of authenticating users with a variety of authenticators while improving overall protection.

## Prerequisites

1. ForgeRock Identity Management (openidm)
1. Axiad Cloud tenant or Axiad Unified Credential Management System (UCMS)
1. Appropriate SCIM connector configurations

## Axiad Configuration

If your Axiad environment is already configuered with required mappings in Axiad Unified Credential Management System (UCMS) there is no additional configuration needed. If assistance is needed with your Axiad environment in the following sections please contact [Axiad Customer Success](mailto:customer.success@axiad.com).

## Configuring the SCIM Connector

1. Get the latest SCIM Connector configuration and mapping file from the [Axiad Customer Success Representative](mailto:customer.success@axiad.com).
2. Copy the provisioner.openicf-AxiadSCIMConnector.json file into the `conf` directory where ForgeRock Identity Management is deployed.
3. Copy the content of mapping-AxiadSCIMConnector.json inside mappings array in `conf\sync.json` file.

## ForgeRock Configuration
### Axiad SCIM Connector Configuration
1. Log into the ForgeRock Identity Management console.
2. Click on `CONFIGURE` and select `CONNECTORS`. AxiadSCIMConnector will be avaiable to configure as shown


   <img src="./images/Axiad_SCIM_Connector.png" width="1000" height="500" align="left"/>
   
4. Click on the Axiad SCIM Connector
   1. Configure the `SCIM Endpoint` under `Base Connector Details` section as shown. If you don't have the endpoint please contact [Axiad Customer Success Representative](mailto:customer.success@axiad.com).
   ![SCIM Endpoint](./images/SCIM_endpoint_config.png)
   2. Confgiure `Authentication token` under `Additional Options` section as shown. If you don't have the token please contact [Axiad Customer Success Representative](mailto:customer.success@axiad.com).
   ![Authentication Token](./images/Authentication_token_config.png)
   3. Click on save.

### Axiad SCIM Connector mappings Configuration   
5. Click on `CONFIGURE` and select `Mappings`. Axiad SCIM mappings will be available as shown below
   ![Axiad SCIM Mappings](./images/Axiad_SCIM_Mappings.png)

### Users mappings Configuration 
6. Click on `Edit` where SOURCE is `Managed/User` and verify the settings are correct
   1. Verify `Properties` tab has mappings as shown below
      ![User_properties_tab](./images/users_mapping/User_properties_tab.png **=100x100**)
   2. Verify `Association Rules` under Association tab has config as shown
      ![User_association_tab]](./images/users_mapping/User_association_tab.png)
      1. Under `Association Rules`, click on pencil icon to verify the `Correlation Query` config as shown
         ![User_correlation_query]](./images/users_mapping/User_correlation_query.png)
   3. Verify `Behaviors` tab has policies as shown
      ![User_behaviors_tab]](./images/users_mapping/User_behaviors_tab.png)
   4. Verify `Advanced` tab has policies as shown 
      ![User_advanced_tab](./images/users_mapping/User_advanced_tab.png)  
       
7. Under scheduling tab, you can `Add Reconciliation Schedule` as per your organization's requirement. 