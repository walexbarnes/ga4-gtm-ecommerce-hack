# ga4-gtm-ecommerce-hack

Developers had data layer specifications for eCommerce tracking in GA4, but no budget for remediation. They deployed a `view_item_list event` when someone viewed a product page, but each item had a `quantity` of `0`. 

![Dev Push Here](https://github.com/walexbarnes/ga4-gtm-ecommerce-hack/blob/main/WOCC_dev_push.png)


Instead of losing this reporting, I intercepted the `view_item_list` event, altered the individual quantities, and re-deployed an individual `view-item` event to the data layer for each product in the array. 

![GTM Fix Here](https://github.com/walexbarnes/ga4-gtm-ecommerce-hack/blob/main/WOCC-view-item-fix.png)

Once that was configured, I just had to add the `view_item` event as a trigger to the pre-existing GA4 eCommerce tag. 

![GA4 eCom Here](https://github.com/walexbarnes/ga4-gtm-ecommerce-hack/blob/main/ga4_ecom.png)

And voila, we have tracking! Ideal? No. Reliable? Technically. Better than no data? I'd say so. 

![GA4 eCom Here](https://github.com/walexbarnes/ga4-gtm-ecommerce-hack/blob/main/final_report.png)
