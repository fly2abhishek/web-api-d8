## Why write code, when you can use Drupal Console?  <!-- .element: class="front-title" -->
![](img/drupal-console.png) <!-- .element: class="logo" -->

Abhishek Anand



## What is console?

>The Drupal CLI. A tool to generate boilerplate code, interact with and debug Drupal.

Note: This will only appear in the speaker notes window.


## The maintainers
<table>
	<tr>
		<td>
			<img alt='jmolivas' class='img-circle' src='https://avatars.githubusercontent.com/u/366275?v=3&amp;s=140' width='140'>
			<div class='overbox'>
				<p>
					<a href='https://github.com/jmolivas' target='_blank'><i class='fa fa-github'></i></a> <a href='https://twitter.com/jmolivas' target='_blank'><i class='fa fa-twitter'></i></a> <a href='http://jmolivas.com' target='_blank'><i class='fa fa-globe'></i></a>
				</p>
			</div>
		</td>
		<td>
			<img alt='enzolutions' class='img-circle' src='https://avatars.githubusercontent.com/u/907914?v=3&amp;s=140' width='140'>
			<div class='overbox'>
				<p>
					<a href='https://github.com/enzolutions' target='_blank'><i class='fa fa-github'></i></a> <a href='https://twitter.com/enzolutions' target='_blank'><i class='fa fa-twitter'></i></a> <a href='http://enzolutions.com/' target='_blank'><i class='fa fa-globe'></i></a>
				</p>
			</div>
		</td>
		<td>
			<img alt='omero' class='img-circle' src='https://avatars.githubusercontent.com/u/1909779?v=3&amp;s=140' width='140'>
			<div class='overbox'>
				<p>
					<a href='https://github.com/omero' target='_blank'><i class='fa fa-github'></i></a> <a href='https://twitter.com/omers' target='_blank'><i class='fa fa-twitter'></i></a> 
				</p>
			</div>
		</td>
		<td>
			<img alt='dmouse' class='img-circle' src='https://avatars.githubusercontent.com/u/198571?v=3&amp;s=140' width='140'>
			<div class='overbox'>
				<p>
					<a href='https://github.com/dmouse' target='_blank'><i class='fa fa-github'></i></a> <a href='https://twitter.com/dmouse' target='_blank'><i class='fa fa-twitter'></i></a> <a href='http://dmouse.net' target='_blank'><i class='fa fa-globe'></i></a>
				</p>
			</div>
		</td>
	</tr>
	<tr>
		<td>
			<h4>
				Jesús Manuel Olivas
			</h4>
		</td>
		<td>
			<h4>
				Eduardo Garcia
			</h4>
		</td>
		<td>
			<h4>
				Omar Aguirre
			</h4>
		</td>
		<td>
			<h4>
				David Flores
			</h4>
		</td>
	</tr>
</table>
[And many more...](https://drupalconsole.com/contributors)


## How is it different from drush?
* Drupal console is a 'from the-ground-up' Drupal CLI tool that leverages Symphony CLI components and modern PHP OOP design practices. 
* Drush is a venerable Drupal CLI tool that has been around since Drupal 4.7, thus built with an older design practice.
* There is overlap based on both projects being a general purpose Drupal administration CLI tool. 
* Drush has more features, due to its age, but Drupal Console has some new features due to its more modern design.


<table>
     <thead>
          <tr>
               <th scope="col">
               <h4>Drush Features</h4>
               </th>
               <th scope="col">
               <h4>Drupal Console Features</h4>
               </th>
          </tr>
     </thead>
     <tbody>
          <tr>
               <td>
               <ul>
                    <li>Download Drupal</li>
                    <li>Download contrib modules</li>
                    <li>Install Drupal</li>
                    <li>Update Drupal and contrib module versions</li>
                    <li>Run updatedb</li>
                    <li>Clear the cache</li>
                    <li>Run cron</li>
                    <li>Run Drupal with a lightweight web server</li>
                    <li>Import, export and merge configuration</li>
                    <li>Add users and set their roles</li>
                    <li>Add permissions to roles</li>
                    <li>Back up and restore Drupal</li>
                    <li>Copy your database and files to a remote server</li>
                    <li>Compile twig templates</li>
               </ul>
               </td>
               <td>
               <ul>
                    <li>Generate code for a:
                    <ul>
                         <li>Console command</li>
                         <li>Content type</li>
                         <li>Controller</li>
                         <li>Entity</li>
                         <li>Form alter hook</li>
                         <li>Module</li>
                         <li>Field type, widget and formatter</li>
                         <li>Image effect</li>
                         <li>Rest resource</li>
                         <li>Service</li>
                         <li>Theme</li>
                    </ul>
                    </li>
                    <li>Switch maintenance mode on or off</li>
                    <li>Run unit tests</li>
               </ul>
               </td>
          </tr>
     </tbody>
</table>



## What the big deal?

* Say bye to writing your module/theme from the scratch. <!-- .element: class="fragment" -->
* Its multilingual, yes you can write cli commands in: <!-- .element: class="fragment" -->
  * हिन्दी <!-- .element: class="fragment" -->
  * मराठी  <!-- .element: class="fragment" -->
  * or 19 languages <!-- .element: class="fragment" -->
* Debug Drupal <!-- .element: class="fragment" -->



## Installing Drupal Console

Using curl:<!-- .element: class="fragment" -->

```
$ curl https://drupalconsole.com/installer -L -o drupal.phar
```
<!-- .element: class="fragment" -->
Or if you don't have curl:<!-- .element: class="fragment" -->

```
$ php -r "readfile('https://drupalconsole.com/installer');" > drupal.phar
```
<!-- .element: class="fragment" -->

Move the executable to bin: <!-- .element: class="fragment" -->
```
mv drupal.phar /usr/local/bin/drupal
```
<!-- .element: class="fragment" -->
Allow execute permissions:<!-- .element: class="fragment" -->
```
chmod +x /usr/local/bin/drupal
```
<!-- .element: class="fragment" -->
Initialize drupal console:<!-- .element: class="fragment" -->
```
drupal init --override
```
<!-- .element: class="fragment" -->


## Using Composer
* Install Drupal Console globally using composer:
<!-- .element: class="fragment" -->
```
$ composer global require drupal/console:@stable
```
<!-- .element: class="fragment" -->
* Add the binary directory to your class path: <!-- .element: class="fragment" -->

```
$ echo "PATH=$PATH:~/.composer/vendor/bin" >> ~/.bash_profile
```
<!-- .element: class="fragment" -->


## Install per site
It is recommended to install Drupal Console per site.  <!-- .element: class="fragment" -->
```
$ composer require drupal/console:@stable --prefer-dist --optimize-autoloaded

$ drupal init --override
```
 <!-- .element: class="fragment" -->


## Install in other languages
```
$ composer require drupal/console-hi
```
 <!-- .element: class="fragment" -->
Will install Drupal Console in Hindi.
 <!-- .element: class="fragment" -->


```
./vendor/bin/drupal list
Drupal Console version 1.0.0-rc8

 प्रयोग:
  कमांड [options] [arguments]

विकल्प:
  -h, --help             Display this help message
  -q, --quiet            Do not output any message
  -V, --version          Display this application version
      --ansi             Force ANSI output
      --no-ansi          Disable ANSI output
  -n, --no-interaction   Do not ask any interactive question
  -e, --env[=ENV]        पर्यावरण का नाम। [default: "prod"]
      --root[=ROOT]      कमाण्ड चलाने के लिए Drupal रूट परिभाषित करें
      --no-debug         डिबग विधि को बंद कर देता है।
      --learning         शब्दबहुल कोड उत्पन्न करें।
  -c, --generate-chain   निष्पादन विकल्प में प्रिंट और तर्क को YAML आउटपुट के रूप में श्रृंखला कमांड में इस्तेमाल किया जाएगा
  -i, --generate-inline  निष्पादन विकल्प में प्रिंट और तर्क को इनलाइन कॉल के रूप में भविष्य में उपयोग किया जाएगा
  -d, --generate-doc     कमाण्ड विकल्पों और तर्क जैसा नीचे निशान
  -t, --target[=TARGET]  साइट का नाम आप (स्थानीय या दूरस्थ साइटों के लिए ) के साथ बातचीत करना चाहते हैं
  -l, --uri=URI          Drupal यूआरआई साइट का(एकाधिक वातावरण के लिए या एक वैकल्पिक port पर चलते समय ) का उपयोग करे
  -y, --yes              स्किप कन्फर्मेशन और आगे बढ़ें
  -v|vv|vvv, --verbose   Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

उपलब्ध कमांड:
  _completion                       BASH completion hook.
  about                             Drupal कंसोल परियोजना के बारे मे प्रारंभिक जानकारी दिखाएँ
  chain                             कमाण्डो को श्रंखला में चलायें।
  check                             System requirement checker
  complete                          Shell पूरा होने के कमांड लिस्ट
  exec                              Execute an external command.
  help                              एक कमांड के लिए मदद प्रदर्शित करता है
  init                              उपयोगकर्ता के होम डायरेक्टरी के लिए कॉन्फ़िगरेशन फाइल कॉपी किया है।
  list                              कमांड की सूची
  server                            PHP निर्मित वेब सर्वर चलायॆ
 breakpoints
  breakpoints:debug                 Displays breakpoints available in application
 cache
  cache:context:debug               Displays current cache context for the application.
  cache:rebuild                     सभी साइट caches को पुनर्निर्माण और साफ़ करें।
 chain
  chain:debug                       श्रृंखला फ़ाइलें की सूचि उपलब्द।
 config
  config:debug                      वर्तमान व्यवस्था को दिखाएँ।
  config:delete                     Delete configuration
  config:diff                       आउटपुट विन्यास आइटम है कि एक डायरेक्टरी के साथ तुलना में सक्रिय कॉन्फ़िगरेशन में अलग हैं।
  config:edit                       चयनित व्यवस्था को बदलें।
  config:export                     मौजूदा एप्लीकेशन कॉन्फ़िगरेशन एक्सपोर्ट करे।
  config:export:content:type        किसी विशेष कंटेंट टाइप और उनके खानो का एक्सपोर्ट करें।
  config:export:single              एक कॉन्फिग को yml फाइल के जैसे निर्यात करें।
  config:export:view                एक व्यू को YAML संरूप में एक्सपोर्ट करें ताकि वो किसी दूसरे वेबसाइट में पुनर्प्रयोग किया जाये।
  config:import                     वर्तमान अनुप्रयोग में व्यवस्था आयात करें।
  config:import:single              Import the selected configuration.
  config:override                   व्यवस्था निधि को सक्रिय डायरेक्टरी में चढ़ा दें।
  config:settings:debug             सेटिंग्स फाइल पर वर्तमान key:value दिखाता है।
 container
  container:debug                   अनुप्रयोग की वर्तमान सर्विसेज़ को दिखाएँ।
 create
  create:comments                   अपने Drupal 8 एप्लीकेशन के लिए डमी कमेंट्स बनाएँ।
  create:nodes                      अपने Drupal 8 एप्लीकेशन के लिए डमी नोड्स बनाएँ।
  create:terms                      अपने Drupal 8 एप्लीकेशन के लिए डमी टर्म्ज़ बनाएँ।
  create:users                      अपने Drupal 8 एप्लीकेशन के लिए डमी यूजरस बनाएँ।
  create:vocabularies               अपने Drupal 8 एप्लीकेशन के लिए डमी वोकैब्युलरीस बनाएँ।
 cron
  cron:debug                        क्रॉन लागू करने वाले मोड्यूलों की सूचि
  cron:execute                      क्रॉन लागू करने वाले किसी विशेष मोड्यूल को चलायें या सारे क्रॉन चलायें
  cron:release                      क्रॉन चलाने के लिए क्रॉन प्रणाली का लॉक को मुक्त करें
 database
  database:client                   लॉन्च एक DB क्लाइंट अगर यह उपलब्ध है
  database:connect                  लॉन्च एक DB क्लाइंट अगर यह उपलब्ध है
  database:drop                     एक दिए गए डेटाबेस में सभी टेबल्स ड्राप।
  database:dump                     डंप संरचना और MYSQL का कंटेंट डेटाबेसेस और टेबल्स
  database:log:clear                DBLog टेबल से इवेंट्स निकालें, फिल्टर उपलब्ध हैं
  database:log:debug                एप्लीकेशन के लिए वर्तमान लॉग इवेंट्स को प्रदर्शित करे
  database:restore                  MYSQL डाटाबेस और टेबल्स ले कंटेंट और संरचना को रिस्टोर करे
  database:table:debug              एक दिए गए डेटाबेस में सभी टेबल्स दिखाएँ.
 entity
  entity:delete                     commands.entity.delete.description
 event
  event:debug                       वर्तमान इवेंट्स को प्रदर्शित करें
 field
  field:info                        commands.field.info.description
 generate
  generate:authentication:provider  प्रमाणन प्रदाता उत्पन्न करें
  generate:breakpoint               Generate breakpoint
  generate:command                  कंसोल के लिए कमाण्डो को उत्पन्न करें।
  generate:controller               एक कंट्रोलर को उत्पन्न और पंजीकृत करें
  generate:doc:cheatsheet           कमांड्स के लिए एक प्रिंटेबल चीट शीट उत्पन्न करें
  generate:doc:dash                 डैश के लिए  DrupalConsole.docset पैकेज उत्पन्न करें
  generate:doc:data                 Generate documentations for Commands.
  generate:doc:gitbook              कमाण्डो के लिए डॉक्युमेंटेशन्स उत्पन्न करें
  generate:entity:bundle            एक नया कंटेंट प्रकार उत्पन्न करें (नोड/एंटिटी बंडल)
  generate:entity:config            एक नया कॉन्फिग एंटिटि उत्पन्न करे
  generate:entity:content           एक नई कंटेंट एंटिटि बनाए
  generate:event:subscriber         एक घटना ग्राहक उत्पन्न करें
  generate:form                     एक नया "%s" उत्पन्न करें
  generate:form:alter               एक hook_form_alter() या hook_form_FORM_ID_alter कार्यान्वयन उत्पन्न करें
  generate:form:config              commands.generate.form.description
  generate:help                     Generate an implementation of hook_help()
  generate:module                   मोड्यूल उत्पन्न करें।
  generate:module:file              Generate a .module file
  generate:permissions              commands.generate.permission.description
  generate:plugin:block             प्लगिन खंड उत्पन्न करें
  generate:plugin:ckeditorbutton    CKEditor बटन प्लगइन उत्पन्न करें।
  generate:plugin:condition         प्लगिन नियम उत्पन्न करें।
  generate:plugin:field             खाना प्रकार, विजेट और formatter प्लगिन उत्पन्न करें।
  generate:plugin:fieldformatter    खाना formatter प्लगिन उत्पन्न करें
  generate:plugin:fieldtype         खाना प्रकार प्लगिन उत्पन्न करें
  generate:plugin:fieldwidget       खाना विजेट प्लगिन उत्पन्न करें
  generate:plugin:imageeffect       छवि प्रभाव प्लगिन उत्पन्न करें
  generate:plugin:imageformatter    छवि formatter प्लगिन उत्पन्न करें
  generate:plugin:mail              एक प्लगइन मेल उत्पन्न करें
  generate:plugin:rest:resource     प्लगिन रेस्ट साधन उत्पन्न करें
  generate:plugin:rulesaction       प्लगिन रुल प्रक्रिया उत्पन्न करें
  generate:plugin:skeleton          Generate an implementation of a skeleton plugin for those plugins Drupal Console do not have a specific generator
  generate:plugin:type:annotation   प्लगिन प्रकार युक्त अननोटेशन प्रकाशन उत्पन्न करें
  generate:plugin:type:yaml         प्लगिन प्रकार युक्त YAML प्रकाशन उत्पन्न करें
  generate:plugin:views:field       विशेष प्लगिन व्यू खाना उत्पन्न करें
  generate:post:update              commands.generate.post:update.description
  generate:profile                  प्रोफाइल उत्पन्न करे.
  generate:routesubscriber          RouteSubscriber उत्पन्न करे.
  generate:service                  सर्विस उत्पन्न करें
  generate:theme                    एक नया थीम उत्पन्न करें।
  generate:twig:extension           Generate a Twig extension.
  generate:update                   Generate an implementation of hook_update_N()
 image
  image:styles:debug                साइट पर इमेज स्टाइल की सूची
  image:styles:flush                Execute flush function by image style or execute all flush images styles
 libraries
  libraries:debug                   Displays libraries available in application
 locale
  locale:language:add               एक भाषा को जोड़े जो आप के साइट द्वारा सपोर्ट होना है
  locale:language:delete            आपकी साइट के द्वारा समर्थित एक भाषा को हटाएँ
  locale:translation:status         सूची उपलब्ध अनुवाद अपडेट
 module
  module:debug                      अनुप्रयोग के उपलब्ध मोड्यूलो को दिखाएँ
  module:dependency:install         commands.module.install.dependencies.description
  module:download                   मोड्यूल या मोड्यूलो को डाउनलोड करें
  module:install                    मोड्यूल या मोड्यूलो को अनुप्रयोग में स्थापित करें
  module:path                       Returns the relative path to the module (or absolute path)
  module:uninstall                  अनुप्रयोग में मॉड्यूल की स्थापित रद्द करें |
  module:update                     Update core, module or modules in the application
 multisite
  multisite:debug                   सभी उपलब्ध multisites की सूची|
  multisite:new                     Sets up the files for a new multisite install.
 node
  node:access:rebuild               Rebuild node access permissions. Rebuilding will remove all privileges to content and replace them with permissions based on the current modules and settings.
 plugin
  plugin:debug                      Display all plugin types, plugin instances of a specific type, or the definition for a specific plugin.
 queue
  queue:debug                       Display the queues of your application
  queue:run                         Process the selected queue.
 router
  router:debug                      अनुप्रयोग के वर्तमान मार्गों को दिखाएँ
  router:rebuild                    अनुप्रयोग के मार्ग पथ को पुनर्निर्माण करें
 settings
  settings:debug                    यूजर Drupal कंसोल सेटिंग्स की सूची
  settings:set                      Drupal कंसोल कॉन्फिग फाइल में एक विशिष्ट सेटिंग मूल्य बदलें
 site
  site:debug                        सभी ज्ञात स्थानीय और दूरस्थ साइटों की सूची दें।
  site:import:local                 Import/Configure एक मौजूदा स्थानीय Drupal परियोजना
  site:install                      एक Drupal परियोजना स्थापित करें
  site:maintenance                  साइट को मेंटेनेंस मोड में बदले
  site:mode                         प्रणाली की कार्य-निष्पादन व्यवस्था को बदलें
  site:statistics                   वेबसाइट के मौजूदा आंकड़े बताते हैं।
  site:status                       वर्तमान Drupal स्थापना के स्थिति को देखें
 state
  state:debug                       वर्तमान स्टेट कीस दिखाएँ।
  state:delete                      Delete State
  state:override                    स्थिति की मौलिक को ओवरराइड करे
 taxonomy
  taxonomy:term:delete              commands.taxonomy.term.delete.description
 theme
  theme:debug                       एप्लीकेशन के लिए वर्तमान थीम्स को प्रदर्शित करता है
  theme:download                    आवेदन में विषय डाउनलोड करे
  theme:install                     इंस्टॉल विषय या विषयों के आवेदन में
  theme:path                        Returns the relative path to the theme (or absolute path)
  theme:uninstall                   विषय की स्थापना रद्द करें या विषयों के आवेदन में
 translation
  translation:cleanup               क्लीनअप ट्रांसलेशन फाइल्स
  translation:pending               पेंडिंग ट्रांसलेशन स्ट्रिंग को एक भाषा में या एक स्पेसिफिक फाइल को एक भाषा में निर्धारण करें
  translation:stats                 ट्रांसलेट स्टैट्स उत्पन्न
  translation:sync                  सींक ट्रांसलेशन फाइल्स
 update
  update:debug                      अनुप्रयोग के उपलब्ध नवीनीकरणो को दिखाएँ
  update:entities                   Applying Entity Updates
  update:execute                    मोड्यूल के किसी विशेष नवीनीकरण N फंक्शन को चलायें या सभी को चलायें।
 user
  user:create                       commands.user.create.description
  user:debug                        एप्लीकेशन के लिए करंट यूजरस को प्रदर्शित करता है
  user:delete                       एप्लीकेशन के लिए यूजरस को हटाये
  user:login:clear:attempts         किसी अकाउंट की असफल लोगिन प्रयासो को साफ़ करें।
  user:login:url                    एक बार काम करने वाली उपभोग्ता लोगिन URL देता है।
  user:password:hash                सरल पासवर्ड से हैश उत्पन्न करें।
  user:password:reset               किसी विशेष उपभोगता का पासवर्ड रिसेट करें
  user:role                         Adds/removes a role for a given user
 views
  views:debug                       अनुप्रयोग के वर्तमान व्यूज साधनो को दिखाएँ
  views:disable                     एक व्यू बंद करें
  views:enable                      एक व्यू चालू करें
  views:plugins:debug               Display current views plugins for the application
 yaml
  yaml:diff                         दो YAML फाइल का अंतर देखने के लिये उनकी तुलना करें
  yaml:get:value                    commands.yaml.get.value.description
  yaml:merge                        एक या एक से ज़्यादा YAML फाइलो को एक YAML फाइल में विलय करें। नवीनीकरण निधि सुरक्षित रहेंगे।
  yaml:split                        इंडेंट द्वारा विभाजन मानदंड से एक YAML फाइल को अलग करें।
  yaml:unset:key                    commands.yaml.unset.key.description
  yaml:update:key                   YAML फाइल में YAML कुंजी को बदले।
  yaml:update:value                 YAML फाइल में किसी विशेष कुंजी के निधि को अवगत करें।
```
 <!-- .element: class="fragment" -->


## Using Drupal Console

```{sh}
$ drupal
Drupal Console (0.11.3) | Supports Drupal (8.0.x) | Current Drupal (8.0.0)
==========================================================================

Copy configuration files to user home directory.

   drupal init --override

Download, install and serve Drupal 8

   drupal chain --file=~/.console/chain/quick-start.yml

Create a new Drupal project

   drupal site:new drupal8.dev 8.0.x

Install a Drupal project

   drupal site:install

Lists all available commands

   drupal list

Update project to the latest version.
-------------------------------------

   drupal self-update
   
```   
 <!-- .element: class="fragment" -->


## Install Drupal with composer
```
composer create-project \
drupal-composer/drupal-project:8.x-dev \
drupal8.dev \
--prefer-dist \
--no-progress \
--no-interaction
```


## Installing Drupal with Drupal console
```
Create a new Drupal project

   drupal site:new drupal8.dev 8.0.x
```


## Install drupal site
```
drupal site:install

 Select Drupal profile to be installed:
  [0] minimal
  [1] standard
 > 1

 Select language for your Drupal installation [Hindi]:
 >

 Drupal Database type:
  [0] MySQL, MariaDB, Percona Server, or equivalent
  [1] SQLite
 > 0

 Database Host [127.0.0.1]:
 >

 Database Name:
 > drupal8_dev

 Database User:
 > root

 Database Pass [ ]:
 >

 Database Port [3306]:
 >

 Database Prefix [ ]:
 >

 Provide your Drupal site name [Drupal 8 Site Install]:
 >

 Provide your Drupal site mail [admin@example.com]:
 >

 Provide your Drupal administrator account name [admin]:
 >

 Provide your Drupal administrator account password:
 >

 Provide your Drupal administrator account mail [admin@example.com]:
 >

 Starting Drupal 8 install process
 ```
<!-- .element: class="fragments" -->
This will get you drupal with drupal console.



## Generate code using Drupal Console
### Lets see that in a demo!

We will see a demo of how to generate
* A module
* A form
* A controller
* A service
* A rest resource


## Generate Module


<video data-autoplay src="video/module.mp4"></video>


## Generate Form 


<video data-autoplay src="video/form.mp4"></video>


## Generate Controller 


<video data-autoplay src="video/controller.mp4"></video>


## Generate Service 


<video data-autoplay src="video/service.mp4"></video>


## Generate REST resource 


<video data-autoplay src="video/rest.mp4"></video>



# Thank You! 
## Questions? <!-- .element: class="fragment" -->
