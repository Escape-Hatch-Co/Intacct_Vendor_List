Intacct Vendor List Module
=============================

Module utilized with [Intacct PHP SDK](https://developer.intacct.com/tools/sdk-php/).

### Help Wanted

Feel Free to add Additional Filters to this module.  At this point there are a very limited number of filters because this Module utilizes the new ["Query" syntax](https://developer.intacct.com/web-services/queries/#advantages-of-query).

### Example Usage:

```php
    /** @var ClientConfig $clientConfig */
    $clientConfig = new ClientConfig();

    $client = new OnlineClient($clientConfig);

    /** @var CustomerList $accountsReceivableRequest **/
    $vendorListRequest = new VendorList();
    $vendorListRequest->setFields(['VENDORID', 'NAME']);

    $filter = new InFilter();
    $filter->setField('VENDORID');
    $filter->addValue('123456');
    $filter->addValue('789012');

    $vendorListRequest->addFilter($filter);

    $response = $client->execute($vendorListRequest);
```
