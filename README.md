gh-pages-publishing
===================

Simple utils to ease publishing to github pages for how we choose to structure our code/documentation.

Expected repository structure
-----------------------------

**&lt;entity>/&lt;code-repo-name>**

Branches:
* gh-pages - where we publish our documentation to and where github expects to find it, and which contains top-level documentation which is not version specific
* Others as required by the library

**&lt;entity>/&lt;code-repo-name>-documentation**

Branches:
* One for each code branch except "gh-pages"

Publishing branch documentation
-------------------------------

Run:

```
./publish.sh <entity/code-repo-name> <branch-name> <github-username>
e.g.
./publish.sh betfair/maven-test-process-plugin master eswdd
```



Which will perform the following:

* Remove all docs from repository &lt;entity/code-repo-name> with branch "gh-pages" in folder &lt;version>
* Copy all docs from repository &lt;entity/code-repo-name>-documentation with branch &lt;version> to that directory
* Generate the maven site for that branch and place in a "maven" subdirectory

Top level docs which are not version specific are held in &lt;entity/code-repo-name> with branch gh-pages.

Licensing
---------

The maven-test-command-plugin-documentation is covered by "[The Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0.html)":

    Copyright 2013, The Sporting Exchange Limited
    
    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at
    
        http://www.apache.org/licenses/LICENSE-2.0
    
    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
