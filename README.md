Magento-Info-Tabs
=================

Add  Tabs to Magento Tabs


####Place THis in Your local.xml file

```xml
<!--
Catalog Product View Layout
-->
<catalog_product_view translate="label">
  <reference name="content">
		<reference name="product.info">
			<block type="catalog/product_view_tabs" name="product.info.tabs" as="info_tabs" template="catalog/product/view/tabs.phtml" >
				<action method="addTab" translate="title" module="catalog"><alias>description</alias><title>Product Description</title><block>catalog/product_view_description</block><template>catalog/product/view/description.phtml</template></action>
				<action method="addTab" translate="title" module="catalog"><alias>upsell_products</alias><title>We Also Recommend</title><block>catalog/product_list_upsell</block><template>catalog/product/list/upsell.phtml</template></action>
				<action method="addTab" translate="title" module="catalog"><alias>additional</alias><title>Additional Information</title><block>catalog/product_view_attributes</block><template>catalog/product/view/attributes.phtml</template></action>
				</block>
		</reference>
	</reference>
</catalog_product_view>  
```

####Add This to the Area you would like you Info Tabs to show up

```php
<?php echo $this->getChildHtml('info_tabs');?>
```
