---
published: false
categories:
  - sample
  - clojure
  - java
  - properties
  - environment
  - turing-complete
  - library
  - environ
  - application-properties
  - snippet
  - zookeeper
  - comparison
---

TODO expand on this post

TODO refactor this post to include the problem first, then the solution

TODO add reference to library ``environ`` (found [here](https://github.com/weavejester/environ))

TODO add example to this in ``environ``: 

(original example from their README)

```lisp
{:dev  {:env {:database-url "jdbc:postgres://localhost/dev"}}
 :test {:env {:database-url "jdbc:postgres://localhost/test"}}}
```

```lisp
(defn get-test-database [type]
  (str "localhost/" type))

{:dev  {:env {:database-url (str "jdbc:postgres://" (get-test-database "dev"))}}
 :test {:env {:database-url "jdbc:postgres://localhost/test"}}}
```

or even

```lisp
(defn get-test-database [type]
  (get-from-webserver "db"))

{:dev  {:env {:database-url (str "jdbc:postgres://" (get-test-database "dev"))}}
 :test {:env {:database-url "jdbc:postgres://localhost/test"}}}
```

--- END example

TODO explain that 

Zookeeper:

> [...] is a centralized service for maintaining configuration information, naming, providing distributed synchronization, and providing group services."
>
> source: https://github.com/liebke/zookeeper-clj

the Apache Zookeeper project's home is [here](http://zookeeper.apache.org/)

The (one-way) maintaining configuration information can be easily done with this system of reading properties

END TODO zookeeper zone

A common ``application.properties``:

```
connection-pool-size=2
username=john.doe
password=1234a
```

With clojure, you can convert this into ``application-properties.clj`` [^1]:

[^1]: the full code can be found in [this file](https://github.com/alvarogarcia7/clojure-simple-sessions/blob/master/test/simple/application-properties.clj)

```lisp
(defn max-connection-pool-size []
  (inc 3))
(defn database-password []
  "1234a")
(defn username[]
  "john.doe")
```

and to read it [^2]:

[^2]: the full code can be found in [this file](https://github.com/alvarogarcia7/clojure-simple-sessions/blob/master/test/simple/repl-session-14.clj)

```lisp
(load-file "test/simple/application-properties.clj")

(max-connection-pool-size)
; 4

(database-password)
; "1234a"

(username)
; "john.doe"
```

As this code is expressed in clojure, arbitrary computations can be expressed (e.g., connect to a server to download the new properties, adjust properties based on system load), instead of the plain properties that can be expressed in a .properties file.

In my opinion, the way of using properties to do complex calculations are breaking the principle "Tell, don't Ask", sample:

```java
[... read application.properties into Properties properties...]

String serviceDiscoveryUrl = properties.get("service-discovery-url");

ServiceDiscovery serviceDiscovery = new ServiceDiscovery(serviceDiscoveryUrl);

List<URI> databases = serviceDiscovery.getDatabases();
List<URI> peers = serviceDiscovery.getPeers();
```

I should not have to tell ``ServiceDiscovery`` how to do this, it should be responsible to handle this itself.

A possible solution would be to move the responsibility of reading the properties to ``ServiceDiscovery`` but then it would have several responsibilities (i.e., reading the properties file, managing the service discovery).

Another possible solution would be to wrap the property-reading with a ``ServiceDiscovery`` (i.e., a dependency), thus moving to something like:

```java
ServiceDiscovery serviceDiscovery = new ServiceDiscovery(new ServiceDiscoveryURLPropertyReader("application.properties"));

List<URI> databases = serviceDiscovery.getDatabases();
List<URI> peers = serviceDiscovery.getPeers();
```

If you think of the first two lines only, this could be moved to an outside component (``ServiceDiscovery``). If we write it in clojure (fragment):

```lisp
(load-file "test/simple/application-properties.clj")
; responsibility of reading the properties file

(databases)
; List<URI>

(peers)
; List<URI>
```

and in the ``test/simple/application-properties.clj``:

```lisp
(defn get-from-webserver [type]
  """Implementation not given. Discovers the URIs for a given type"""
[])

(defn databases[]
  (get-from-webserver "db"))
  
(defn peers[]
  (get-from-webserver "peer"))
```

## Other uses

The properties file can also be seen as a configuration source, i.e., a place where configuration can be stored.

A common case for these configuration files are rules.

Let's take a validation example: describing validation rules in a DSL

A first take would be to create an engine plus ``eval``uable rules.

Example: 

Java engine + XML/Json/YAML rules

TODO Is the problem about being practical or theoretically possible?
  
  You could have Java code in the configuration file and then javac that code into valid java bytecode to be executed.

  If your write it in javascript, the problem is reduced because you can use the eval function.

TODO: S-Expressions are not considered Turing-complete, although it doesn't cite a source. https://en.wikipedia.org/wiki/Turing_completeness . Search for S-Expression


## Example

```lisp
(def configuration 
	{:isServiceEnabled true
	 :serviceLocation "http://localhost:5000/op/"
	 :version "v1"
	 })

(defn load-configuration [defaultConfig newconfig]
	(if (newer? newconfig defaultConfig)
		newconfig
		defaultConfig))

(defn newer? [c1 c2]
	(> (:version c1) (:version c2)))

(cond
	(a > 1) true
	(a > 2) 8
	:default false)

(def configuration-rules {
	:isServiceEnabled
		{
			:possible-values [true, false]
			:mandatory true
			:forces [:endpoint]
		}

	:endpoint
		{
			:mandatory false
			:requires [:isServiceEnabled]
			:is-valid? (fn (or 
				(fn [n] (> n 9))
				(fn [n] (= n -1))))
		}
})
```
