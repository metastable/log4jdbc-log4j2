<p>
<strong>log4jdbc-log4j2</strong> is a modification of <a
rel="nofollow" title="External link to log4jdbc"
href="/web/20160118062235/http://code.google.com/p/log4jdbc/">log4jdbc</a>
to natively use Log4j 2 (or SLF4J as usual), that supports JDBC 4.1 to
JDBC 3, includes all the improvements of log4jdbc-remix, and provides
new improvements on its own. log4jdbc-log4j2:
</p>
<ul>
<li>natively supports <a rel="nofollow"
title="External link to log4j 2"
href="/web/20160118062235/http://logging.apache.org/log4j/2.x/">Log4j
2</a>. <a rel="nofollow" title="External link to SLF4J"
href="/web/20160118062235/http://www.slf4j.org/">SLF4J</a> can still
be used as usual.
</li>
<li>supports JDBC 4.1 (Java 7), JDBC 4 (Java 6), JDBC 3 (Java 5).</li>
<li>includes all the improvements of <a rel="nofollow"
title="External link to log4jdbc-remix"
href="/web/20160118062235/http://code.google.com/p/log4jdbc-remix/">log4jdbc-remix</a>
(can log result sets as tables, can be configured as a <tt>Datasource</tt>,
can use a plugable SQL formatter).
</li>
<li>is available in the sonatype maven repository.</li>
<li>provides new improvements on its own (logging of connection
opening execution time, of <tt>getGeneratedKeys()</tt> queries, etc)
</li>
</ul>
<hr>
<p></p>
<p></p>
<h1>News</h1>
<ul>
<li><strong>2013-12-12: </strong>Release of log4jdbc-logj2 1.16:
fixes <a
href="/web/20160118062235/https://code.google.com/p/log4jdbc-log4j2/issues/detail?id=8"
class="closed_ref"
title="log4jdbc.debug.stack.prefix option as REGEX not work for slf4j">&nbsp;issue
#8&nbsp;</a>, <a
href="/web/20160118062235/https://code.google.com/p/log4jdbc-log4j2/issues/detail?id=9"
class="closed_ref"
title="NullPointerException on empty result set running against Oracle">&nbsp;issue
#9&nbsp;</a>, and <a
href="/web/20160118062235/https://code.google.com/p/log4jdbc-log4j2/issues/detail?id=10"
class="closed_ref" title="Spring @Scheduled method">&nbsp;issue
#10&nbsp;</a>.</li>
<p></p>
<p></p>
<li><strong>2013-06-21: </strong>Release of log4jdbc-logj2 1.15:
several bug fixes related to the print of the result sets as table
(because of modifications in this implementation as compared to
log4jdbc-remix).</li>
<p></p>
<p></p>
<li><strong>2013-06-20: </strong>Release of log4jdbc-logj2 1.14:
bug fixes and improvements from the log4jdbc-remix trunk, notably the
ability to provide different SQL loggers to different data sources
(see <a rel="nofollow"
href="/web/20160118062235/http://code.google.com/p/log4jdbc-remix/issues/detail?id=9">http://code.google.com/p/log4jdbc-remix/issues/detail?id=9</a>).</li>
<p></p>
<p></p>
<li><strong>2013-06-19: </strong>Release of log4jdbc-logj2 1.13:
bug fix (see <a
href="/web/20160118062235/https://code.google.com/p/log4jdbc-log4j2/issues/detail?id=4"
class="closed_ref"
title="java.sql.SQLException: Closed Resultset: getMetaData">&nbsp;issue
#4&nbsp;</a>).</li>
<p></p>
<p></p>
<li><strong>2013-04-25: </strong>Release of log4jdbc-logj2 1.12:
Adding fixes that were committed to the main log4jdbc branch after
the last official release.</li>
<p></p>
<p></p>
<li><strong>2013-04-23: </strong>Release of log4jdbc-logj2 1.11:
Clearer error message when no proper logging system can be found.
Availability on the Sonatype maven repository (finally!).</li>
<p></p>
<p></p>
<li><strong>2013-03-31: </strong>Release of log4jdbc-logj2 1.1:
Major update to include all the improvements of log4jdbc-remix,
provide support for JDBC 4.1, to allow the use of solely one logger
library (either Log4j 2 or SLF4J), and to add several unit tests.</li>
<p></p>
<p></p>
<li><strong>2012-11-14: </strong>Release of log4jdbc-logj2 1.01:
minor modification to adapt to a change of API in log4j 2.0 beta2
(the previous release was based on log4j 2.0 alpha2 SNAPSHOT)</li>
<p></p>
<p></p>
<li><strong>2012-09-05: </strong>log4jdbc-logj2 1.0 is out.</li>
</ul>
<hr>
<p></p>
<p></p>
<h1>Advantages</h1>
<h2>One single logger</h2>
<p>Thanks to the use of the features provided by Log4j 2, only one
single logger is needed to be configured, as opposed to five in the
standard implementation of log4jdbc (and six when using
log4jdbc-remix). The standard log4jdbc behavior can still be easily
reproduced (see below for more details). You can nevertheless use
SLF4J and configure several loggers as in the standard log4jdbc
implementation if you wish to do so.</p>
<p></p>
<p></p>
<h2>log4jdbc-remix features</h2>
<p>
All the improvements provided by log4jdbc-remix are included in this
implementation: can log result sets as tables, can be configured as a
<tt>Datasource</tt>
, can use a custom SQL formatter, is available in the sonatype maven
repository. If you use Log4j 2, the logging of the result sets are
still configurable with a single logger. Also note that this
implementation provides an additional way of configuring a custom SQL
formatter, through properties (see below).
</p>
<p></p>
<p></p>
<h2>JDBC 4.1 support</h2>
log4jdbc-log4j2 supports JDBC 4.1 (JDK 1.7), JDBC 4 (JDK 1.6), JDBC 3
(JDK 1.5). Please note that we do not provide a JDBC 3 version for JDK
1.4.
<p></p>
<p></p>
<h2>Easy dispatch in different files of different SQL operations</h2>
<p>Thanks to the use of the features provided by Log4j 2, you can
easily dispatch different SQL operations (SELECT, UPDATE, ...) or
errors (Exception thrown) in different files . This is not doable
using the standard implementation of log4jdbc.</p>
<p></p>
<p></p>
<h2>Availability in the sonatype maven repository</h2>
<p>
log4jdbc-log4j2 is available through the Maven repository: group
<tt>org.bgee.log4jdbc-log4j2</tt>
, artifacts
<tt>log4jdbc-log4j2-jdbc3</tt>
,
<tt>log4jdbc-log4j2-jdbc4</tt>
, and
<tt>log4jdbc-log4j2-jdbc4.1</tt>
.
</p>
<p></p>
<p></p>
<h2>Other improvements</h2>
<p>
This implementation provides some slight improvements, for instance:
execution time for connection opening and closing, calls to
<tt>Statement.getGeneratedKeys()</tt>
logged along with the SQL query it was performed on, etc.
</p>
<hr>
<p></p>
<p></p>
<h1>Installation</h1>
Installation is almost the same as with the standard version of
log4jdbc.
<strong>But be careful with the slight modifications</strong>, notably:
<ul>
<li>the name of the <tt>Driver</tt> to load is different than in
the standard log4jdbc implementation (but if you use the JDBC 4 or
JDBC 4.1 versions, you do not need to load the <tt>Driver</tt>
yourself anyway, log4jdbc-log4j2 will be automatically discovered and
loaded).
</li>
<li>If you choose to use SLF4J rather than Log4j 2, you need to
configure the option <tt>log4jdbc.spylogdelegator.name</tt> to the
value <tt>net.sf.log4jdbc.log.slf4j.Slf4jSpyLogDelegator</tt> (see
below for more details).
</li>
</ul>
<p></p>
<p></p>
<h2>1. Install log4jdbc-log4j2</h2>
<h3>1.1. Decide if you need JDBC 3, JDBC 4, or JDBC 4.1 support.</h3>
<p>Depending on which JDK you use, you should install different
versions of log4jdbc-log4j2:</p>
<ul>
<li>If you are using Java 5, you should use the JDBC 3 version of
log4jdbc-log4j2.</li>
<li>For Java 6, the JDBC 4 version of log4jdbc-log4j2.</li>
<li>For Java 7, the JDBC 4.1 version of log4jdbc-log4j2.</li>
</ul>
<p></p>
<p>You should make your choice based on which JDK version you use,
rather than which JDBC version: for instance, the log4jdbc JDBC 4
driver can wrap a JDBC 3 or older driver, as long as you don't call
any unsupported method.</p>
<p></p>
<p></p>
<h3>1.2. Option 1: installation via direct download</h3>
<p>Choose and download one of the driver .jar files:</p>
<ul>
<li><a rel="nofollow" title="Download log4jdbc-log4j2 for JDBC3"
href="/web/20160118062235/http://log4jdbc-log4j2.googlecode.com/files/log4jdbc-log4j2-jdbc3-1.16.jar">log4jdbc-log4j2-jdbc3.jar</a>
for JDBC 3 support in JDK 1.5. Please note that starting from version
<tt>beta5</tt>, Log4j 2 is compiled using JDK 1.6, so that
log4jdbc-log4j2 for JDBC3 is usable with no later version than Log4j
2 <tt>beta4</tt>.</li>
<li><a rel="nofollow" title="Download log4jdbc-log4j2 for JDBC4"
href="/web/20160118062235/http://log4jdbc-log4j2.googlecode.com/files/log4jdbc-log4j2-jdbc4-1.16.jar">log4jdbc-log4j2-jdbc4.jar</a>
for JDBC 4 support in JDK 1.6</li>
<li><a rel="nofollow"
title="Download log4jdbc-log4j2 for JDBC4.1"
href="/web/20160118062235/http://log4jdbc-log4j2.googlecode.com/files/log4jdbc-log4j2-jdbc4.1-1.16.jar">log4jdbc-log4j2-jdbc4.1.jar</a>
for JDBC 4.1 support in JDK 1.7</li>
</ul>
Place the log4jdbc-log4j2 jar that you chose into your application's
classpath.
<p></p>
<p></p>
<p></p>
<h3>1.3. Option 2: installation via Maven repository</h3>
Add the following to your
<tt>pom.xml</tt>
configuration file, replace
<tt>log4jdbc-log4j2-jdbcXX</tt>
by the value corresponding to the JDBC version you want to use (either
<tt>log4jdbc-log4j2-jdbc4.1</tt>
, or
<tt>log4jdbc-log4j2-jdbc4</tt>
, or
<tt>log4jdbc-log4j2-jdbc3</tt>
):
<p></p>
<pre class="prettyprint">
<span class="tag">&lt;dependency&gt;</span><span class="pln"><br>&nbsp; </span><span
class="tag">&lt;groupId&gt;</span><span class="pln">org.bgee.log4jdbc-log4j2</span><span
class="tag">&lt;/groupId&gt;</span><span class="pln"><br>&nbsp; </span><span
class="tag">&lt;artifactId&gt;</span><span class="pln">log4jdbc-log4j2-jdbcXX</span><span
class="tag">&lt;/artifactId&gt;</span><span class="pln"><br>&nbsp; </span><span
class="tag">&lt;version&gt;</span><span class="pln">1.16</span><span
class="tag">&lt;/version&gt;</span><span class="pln"><br></span><span
class="tag">&lt;/dependency&gt;</span>
</pre>
<p></p>
<h2>2. Install the logging library you want to use</h2>
<h3>2.1. If you want to use Log4j 2 (recommended choice)</h3>
<p>
Get the last version of Log4j 2, either from their <a rel="nofollow"
title="External link to log4j 2"
href="/web/20160118062235/http://logging.apache.org/log4j/2.0/download.html">download
page</a>, or from their <a rel="nofollow"
title="External link to log4j 2"
href="/web/20160118062235/http://logging.apache.org/log4j/2.x/build.html">Maven
repository</a> (this link contains instructions to configure your
<tt>pom.xml</tt>
file).
</p>
<p></p>
<p></p>
<p>
You will typically need to install the
<tt>log4j-core</tt>
and
<tt>log4j-api</tt>
libraries. Please note that starting from version
<tt>beta5</tt>
, Log4j 2 is compiled using JDK 1.6, so that log4jdbc-log4j2 for JDBC3
is usable with no later version than Log4j 2
<tt>beta4</tt>
.
</p>
<p></p>
<p></p>
<h3>2.2. If you want to use SLF4J</h3>
<p>
Get the last version of SLF4J, either from their <a rel="nofollow"
title="External link to SLF4J"
href="/web/20160118062235/http://www.slf4j.org/download.html">download
page</a>, or from their <a rel="nofollow" title="SLF4J Maven repository"
href="/web/20160118062235/http://mvnrepository.com/artifact/org.slf4j">Maven
repository</a>.
</p>
<p></p>
<p></p>
<p>
You will need at least two libraries: the
<tt>slf4j-api</tt>
library, and whichever library you pick depending on the java logging
system you choose (for instance, Log4j, java.util logging, logback,
Jakarta Commons Logging).
</p>
<p></p>
<h2>3. Modification of your source code</h2>
<h3>3.1. Change your JDBC URL</h3>
Prepend
<strong><tt>jdbc:log4</tt></strong> to the normal JDBC URL that you are
using. For example, if your normal JDBC URL is:
<p></p>
<pre class="prettyprint">
<span class="pln">&nbsp; &nbsp; &nbsp; jdbc</span><span class="pun">:</span><span
class="pln">derby</span><span class="pun">:</span><span class="com">//localhost:1527//db-derby-10.2.2.0-bin/databases/MyDatabase</span>
</pre>
<p>then you would change it to:</p>
<pre class="prettyprint">
<span class="pln">&nbsp; &nbsp; &nbsp; jdbc</span><span class="pun">:</span><span
class="pln">log4jdbc</span><span class="pun">:</span><span
class="pln">derby</span><span class="pun">:</span><span class="com">//localhost:1527//db-derby-10.2.2.0-bin/databases/MyDatabase</span>
</pre>
<p>to use log4jdbc-log4j2.</p>
<p></p>
<h3>3.2. Change the driver used</h3>
<p>
Set your JDBC driver class to <strong><tt>net.sf.log4jdbc.sql.jdbcapi.DriverSpy</tt></strong>
in your application (please note that this is not the same class name
as in the standard log4jdbc implementation). See the <a rel="nofollow"
title="External link to log4jdbc"
href="/web/20160118062235/http://code.google.com/p/log4jdbc/">log4jdbc
documentation</a> to see the list of supported drivers, or how to add
support for other drivers. log4jdbc supports almost all major drivers.
</p>
<p>
Note that it is actually not necessary to set the
<tt>Driver</tt>
to load (through, for instance,
<tt>Class.forName("net.sf.log4jdbc.sql.jdbcapi.DriverSpy")</tt>
) if you use the JDBC 4 or JDBC 4.1 versions. The driver will be
automatically discovered and loaded.
</p>
<p></p>
<p></p>
<h2>4. Set up your logger</h2>
<h3>4.1. If you use Log4j 2</h3>
<p>
Log4jdbc-log4j2 uses only one logger, called <strong><tt>log4jdbc.log4j2</tt></strong>
(while the standard implementation uses 5, and even 6 when using
log4jdbc-remix).
</p>
<p>
Its behavior can be set, notably from a Log4j 2 configuration file.
This documentation presents some examples (see "Usage" below). Almost
all features provided by the standard implementations of log4jdbc and
log4jdbc-remix can be reproduced by using this single logger, thanks
to the use of <a rel="nofollow"
href="/web/20160118062235/http://logging.apache.org/log4j/2.0/manual/markers.html">Markers</a>.
</p>
<p>
This allows a very simple configuration, for instance, at the
<tt>ERROR</tt>
level:
</p>
<pre class="prettyprint">
<span class="tag">&lt;logger</span><span class="pln"> </span><span
class="atn">name</span><span class="pun">=</span><span class="atv">"log4jdbc.log4j2"</span><span
class="pln"> </span><span class="atn">level</span><span class="pun">=</span><span
class="atv">"error"</span><span class="pln"> </span><span class="atn">additivity</span><span
class="pun">=</span><span class="atv">"false"</span><span class="tag">&gt;</span><span
class="pln"><br>&nbsp; </span><span class="tag">&lt;appender-ref</span><span
class="pln"> </span><span class="atn">ref</span><span class="pun">=</span><span
class="atv">"Console"</span><span class="tag">/&gt;</span><span
class="pln"><br></span><span class="tag">&lt;/logger&gt;</span>
</pre>
<p>And that's it!</p>
<p></p>
<p></p>
<p>
This logger is easily configurable via the use of
<tt>Marker</tt>
s. See the "Usage" section below for several examples on how to use
them, or how to reproduce log4jdbc and log4jdbc-remix standard
behaviors. The recommended configuration at
<tt>INFO</tt>
or
<tt>DEBUG</tt>
level is basically:
</p>
<pre class="prettyprint">
<span class="tag">&lt;logger</span><span class="pln"> </span><span
class="atn">name</span><span class="pun">=</span><span class="atv">"log4jdbc.log4j2"</span><span
class="pln"> </span><span class="atn">level</span><span class="pun">=</span><span
class="atv">"info"</span><span class="pln"> </span><span class="atn">additivity</span><span
class="pun">=</span><span class="atv">"false"</span><span class="tag">&gt;</span><span
class="pln"><br>&nbsp; </span><span class="tag">&lt;MarkerFilter</span><span
class="pln"> </span><span class="atn">marker</span><span class="pun">=</span><span
class="atv">"LOG4JDBC_OTHER"</span><span class="pln"> </span><span
class="atn">onMatch</span><span class="pun">=</span><span class="atv">"</span><span
class="pln">DENY</span><span class="atv">"</span><span class="pln"> </span><span
class="atn">onMismatch</span><span class="pun">=</span><span
class="atv">"</span><span class="pln">NEUTRAL</span><span class="atv">"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; </span><span
class="tag">&lt;appender-ref</span><span class="pln"> </span><span
class="atn">ref</span><span class="pun">=</span><span class="atv">"Console"</span><span
class="tag">/&gt;</span><span class="pln"><br></span><span
class="tag">&lt;/logger&gt;</span>
</pre>
<p></p>
<p></p>
<p></p>
<p>Note that if this logger is turned off (or for example, set to a
level less than error, such as the FATAL level), then log4jdbc will
not log anything and in fact the actual real connection to the
underlying database will be returned by the log4jdbc driver (thus
allowing log4jdbc to be installed and available to turn on at runtime
at a moment's notice without imposing any actual performance loss when
not being used).</p>
<h4>
List of all available
<tt>Marker</tt>
s
</h4>
<ul>
<li><tt>LOG4JDBC_EXCEPTION</tt>: associated to all <tt>SQLException</tt>s.
This is useful when the feature of logging slow queries with an <tt>ERROR</tt>
level is activated.</li>
<p></p>
<p></p>
<li><tt>LOG4JDBC_SQL</tt>: associated to SQL statements (to <strong>all</strong>
statements, even different operations than select, update, insert,
delete, or create, for instance: drop). Parent of the following
markers:
<ul>
<li><tt>LOG4JDBC_SELECT</tt>: associated to SQL statements
performing a <tt>SELECT</tt> operation.</li>
<li><tt>LOG4JDBC_UPDATE</tt>: associated to SQL statements
performing a <tt>UPDATE</tt> operation.</li>
<li><tt>LOG4JDBC_INSERT</tt>: associated to SQL statements
performing a <tt>INSERT</tt> operation.</li>
<li><tt>LOG4JDBC_DELETE</tt>: associated to SQL statements
performing a <tt>DELETE</tt> operation.</li>
<li><tt>LOG4JDBC_CREATE</tt>: associated to SQL statements
performing a <tt>CREATE</tt> operation.</li>
</ul></li>
<p></p>
<p></p>
<li><tt>LOG4JDBC_NON_STATEMENT</tt>: associated to all JDBC calls
that are not SQL statements, and to the logging of result sets as
tables (log4jdbc-remix feature). Parent of the following markers:
<ul>
<p></p>
<p></p>
<li><tt>LOG4JDBC_CONNECTION</tt>: logs connection open, close,
and abort events, as well as dump of all open connection numbers
(useful for hunting down connection leak problems).</li>
<p></p>
<p></p>
<li><tt>LOG4JDBC_OTHER</tt>: associated to all JDBC calls,
including calls to <tt>ResultSet</tt>, and to the logging of result
sets as tables (log4jdbc-remix feature). Parent of the following
markers:
<ul>
<p></p>
<p></p>
<li><tt>LOG4JDBC_JDBC</tt>: associated to all JDBC calls,
including calls to <tt>ResultSet</tt>. Parent of the following
markers:
<ul>
<li><tt>LOG4JDBC_AUDIT</tt>: associated to JDBC calls,
except calls to <tt>ResultSet</tt>. This is a very voluminous
output, and is not normally needed unless tracking down a
specific JDBC problem.</li>
<li><tt>LOG4JDBC_RESULTSET</tt>: associated to calls to <tt>ResultSet</tt>.
Produce logs even more voluminous, because all calls to
ResultSet objects are logged.</li>
<p></p>
<p></p>
</ul></li>
<li><tt>LOG4JDBC_RESULTSETTABLE</tt>: <tt>Marker</tt> to log
JDBC <tt>ResultSet</tt>s as table. Functionality inherited from
log4jdbc-remix (corresponds to the <tt>jdbc.resultsettable</tt>
logger in the log4jdbc-remix implementation)</li>
</ul></li>
</ul></li>
</ul>
<p></p>
<p></p>
<h3>4.2. If you use SLF4J</h3>
<h4>
4.2.1 Set the option
<tt>log4jdbc.spylogdelegator.name</tt>
</h4>
<p>
First, you need to tell log4jdbc-log4j2 that you want to use the SLF4J
logger. You need to configure the option
<tt>log4jdbc.spylogdelegator.name</tt>
to the value
<tt>net.sf.log4jdbc.log.slf4j.Slf4jSpyLogDelegator</tt>
. This is done either via the <strong><tt>log4jdbc.log4j2.properties</tt></strong>
file stored in your classpath, or via system properties.
</p>
<p>
Add to the
<tt>log4jdbc.log4j2.properties</tt>
file:
</p>
<pre class="prettyprint">
<span class="pln">log4jdbc</span><span class="pun">.</span><span
class="pln">spylogdelegator</span><span class="pun">.</span><span
class="pln">name</span><span class="pun">=</span><span class="pln">net</span><span
class="pun">.</span><span class="pln">sf</span><span class="pun">.</span><span
class="pln">log4jdbc</span><span class="pun">.</span><span
class="pln">log</span><span class="pun">.</span><span class="pln">slf4j</span><span
class="pun">.</span><span class="typ">Slf4jSpyLogDelegator</span>
</pre>
<p></p>
<p>Or use System properties:</p>
<pre class="prettyprint">
<span class="pln">java </span><span class="pun">-</span><span
class="typ">Dlog4jdbc</span><span class="pun">.</span><span
class="pln">spylogdelegator</span><span class="pun">.</span><span
class="pln">name</span><span class="pun">=</span><span class="pln">net</span><span
class="pun">.</span><span class="pln">sf</span><span class="pun">.</span><span
class="pln">log4jdbc</span><span class="pun">.</span><span
class="pln">log</span><span class="pun">.</span><span class="pln">slf4j</span><span
class="pun">.</span><span class="typ">Slf4jSpyLogDelegator</span><span
class="pln"> </span><span class="pun">-</span><span class="pln">classpath </span><span
class="pun">./</span><span class="pln">classes </span><span
class="kwd">my</span><span class="pun">.</span><span class="pln">funky</span><span
class="pun">.</span><span class="typ">Program</span>
</pre>
<p></p>
<p>
See below for more details about how to configure the options of
log4jdbc-log4j2 (notably, the
<tt>log4jdbc.spylogdelegator.name</tt>
option allows to set any custom SQL formatter).
</p>
<p></p>
<p></p>
<h4>4.2.2. Configure the loggers</h4>
<p>From the log4jdbc and log4jdbc-remix documentation: there are 6
loggers that are used. If all 6 are turned off (or for example, set to
a level less than error, such as the FATAL level in log4j), then
log4jdbc will not log anything and in fact the actual (real)
connection to the underlying database will be returned by the log4jdbc
driver (thus allowing log4jdbc to be installed and available to turn
on at runtime at a moment's notice without imposing any actual
performance loss when not being used). If any of the 5 logs are set to
ERROR level or above (e.g ERROR, INFO or DEBUG) then log4jdbc will be
activated, wrapping and logging activity in the JDBC connections
returned by the underlying driver.</p>
<table class="wikitable">
<tbody>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;"><strong>logger</strong></td>
<td style="border: 1px solid #ccc; padding: 5px;"><strong>description</strong></td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">jdbc.sqlonly</td>
<td style="border: 1px solid #ccc; padding: 5px;">Logs only
SQL. SQL executed within a prepared statement is automatically
shown with it's bind arguments replaced with the data bound at that
position, for greatly increased readability.</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">jdbc.sqltiming</td>
<td style="border: 1px solid #ccc; padding: 5px;">Logs the SQL,
post-execution, including timing statistics on how long the SQL
took to execute.</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">jdbc.audit</td>
<td style="border: 1px solid #ccc; padding: 5px;">Logs ALL JDBC
calls except for ResultSets. This is a very voluminous output, and
is not normally needed unless tracking down a specific JDBC
problem.</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">jdbc.resultset</td>
<td style="border: 1px solid #ccc; padding: 5px;">Even more
voluminous, because all calls to ResultSet objects are logged.</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">jdbc.resultsettable</td>
<td style="border: 1px solid #ccc; padding: 5px;">Log the jdbc
results as a table. Level debug will fill in unread values in the
result set.</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">jdbc.connection</td>
<td style="border: 1px solid #ccc; padding: 5px;">Logs
connection open and close events as well as dumping all open
connection numbers. This is very useful for hunting down connection
leak problems.</td>
</tr>
</tbody>
</table>
<p></p>
<p></p>
<h3>4.3. For both Log4j 2 or SLF4J</h3>
<p>The levels used are the same as in the standard implementation:
</p>
<ul>
<li><tt>DEBUG</tt> includes the class name and line number (if
available) at which the SQL was executed. <strong>Use DEBUG
level with extra care, as this imposes an additional performance
penalty when in use.</strong></li>
<li><tt>INFO</tt> includes the SQL (or other information as
applicable.)</li>
<li><tt>ERROR</tt> includes the stack traces in the log output
when <tt>SQLException</tt>s occur (and slow queries if enabled, see
below).</li>
</ul>
<p></p>
<p>Additionally, there is one logger named log4jdbc.debug which is
for use with internal debugging of log4jdbc. At this time it just
prints out information on which underlying drivers were found and not
found when the log4jdbc spy driver loads.</p>
<hr>
<p></p>
<p></p>
<h1>Usage with Log4j 2</h1>
These examples assume that you configure Log4j 2 through a
<tt>log4j2.xml</tt>
configuration file, placed in your classpath.
<h2>
1. Basic configuration at
<tt>ERROR</tt>
level
</h2>
An example Log4j 2 configuration file: uses the
<tt>log4jdbc.log4j2</tt>
logger, and writes errors (and slow queries if enabled, see below) into
the file
<tt>log4jdbc.out</tt>
:
<p></p>
<pre class="prettyprint">
<span class="pun">&lt;?</span><span class="pln">xml version</span><span
class="pun">=</span><span class="str">"1.0"</span><span class="pln"> encoding</span><span
class="pun">=</span><span class="str">"UTF-8"</span><span class="pun">?&gt;</span><span
class="pln"><br></span><span class="tag">&lt;configuration</span><span
class="pln"> </span><span class="atn">status</span><span class="pun">=</span><span
class="atv">"OFF"</span><span class="tag">&gt;</span><span
class="pln"><br>&nbsp; </span><span class="tag">&lt;appenders&gt;</span><span
class="pln"><br>&nbsp; &nbsp; </span><span class="tag">&lt;Console</span><span
class="pln"> </span><span class="atn">name</span><span class="pun">=</span><span
class="atv">"Console"</span><span class="pln"> </span><span
class="atn">target</span><span class="pun">=</span><span class="atv">"SYSTEM_OUT"</span><span
class="tag">&gt;</span><span class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span
class="tag">&lt;PatternLayout</span><span class="pln"> </span><span
class="atn">pattern</span><span class="pun">=</span><span class="atv">"%d{HH:mm:ss.SSS} [%t] %level - %m%n%ex%n"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;/Console&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;File</span><span class="pln"> </span><span
class="atn">name</span><span class="pun">=</span><span class="atv">"log4jdbc_file"</span><span
class="pln"> </span><span class="atn">fileName</span><span
class="pun">=</span><span class="atv">"log4jdbc.out"</span><span
class="tag">&gt;</span><span class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span
class="tag">&lt;PatternLayout</span><span class="pln"> </span><span
class="atn">pattern</span><span class="pun">=</span><span class="atv">"%d{HH:mm:ss.SSS} [%t] %level - %m%n%ex%n"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;/File&gt;</span><span class="pln"><br>&nbsp; </span><span
class="tag">&lt;/appenders&gt;</span><span class="pln"><br>&nbsp; </span><span
class="tag">&lt;loggers&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;root</span><span class="pln"> </span><span
class="atn">level</span><span class="pun">=</span><span class="atv">"off"</span><span
class="tag">&gt;</span><span class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span
class="tag">&lt;appender-ref</span><span class="pln"> </span><span
class="atn">ref</span><span class="pun">=</span><span class="atv">"Console"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;/root&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;logger</span><span class="pln"> </span><span
class="atn">name</span><span class="pun">=</span><span class="atv">"log4jdbc.log4j2"</span><span
class="pln"> </span><span class="atn">level</span><span class="pun">=</span><span
class="atv">"error"</span><span class="pln"> </span><span class="atn">additivity</span><span
class="pun">=</span><span class="atv">"false"</span><span class="tag">&gt;</span><span
class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span class="tag">&lt;appender-ref</span><span
class="pln"> </span><span class="atn">ref</span><span class="pun">=</span><span
class="atv">"log4jdbc_file"</span><span class="tag">/&gt;</span><span
class="pln"><br>&nbsp; &nbsp; </span><span class="tag">&lt;/logger&gt;</span><span
class="pln"><br>&nbsp; </span><span class="tag">&lt;/loggers&gt;</span><span
class="pln"><br></span><span class="tag">&lt;/configuration&gt;</span>
</pre>
<p></p>
<h2>
2. Recommended configuration at
<tt>INFO</tt>
or
<tt>DEBUG</tt>
level
</h2>
This modified implementation uses
<a rel="nofollow"
href="/web/20160118062235/http://logging.apache.org/log4j/2.0/manual/markers.html">Markers</a>,
rather than different loggers as in the standard implementation. Here
is a configuration example at
<tt>INFO</tt>
or
<tt>DEBUG</tt>
level, to log all relevant information (SQL statements, Connection
calls, Exceptions thrown), and to not log JDBC calls, nor result sets
as tables (overwhelming logs). It is just a matter of adding one line (
<tt>&lt;MarkerFilter...</tt>
):
<p></p>
<pre class="prettyprint">
<span class="tag">&lt;logger</span><span class="pln"> </span><span
class="atn">name</span><span class="pun">=</span><span class="atv">"log4jdbc.log4j2"</span><span
class="pln"> </span><span class="atn">level</span><span class="pun">=</span><span
class="atv">"info"</span><span class="pln"> </span><span class="atn">additivity</span><span
class="pun">=</span><span class="atv">"false"</span><span class="tag">&gt;</span><span
class="pln"><br>&nbsp; </span><span class="tag">&lt;MarkerFilter</span><span
class="pln"> </span><span class="atn">marker</span><span class="pun">=</span><span
class="atv">"LOG4JDBC_OTHER"</span><span class="pln"> </span><span
class="atn">onMatch</span><span class="pun">=</span><span class="atv">"</span><span
class="pln">DENY</span><span class="atv">"</span><span class="pln"> </span><span
class="atn">onMismatch</span><span class="pun">=</span><span
class="atv">"</span><span class="pln">NEUTRAL</span><span class="atv">"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; </span><span
class="tag">&lt;appender-ref</span><span class="pln"> </span><span
class="atn">ref</span><span class="pun">=</span><span class="atv">"log4jdbc_file"</span><span
class="tag">/&gt;</span><span class="pln"><br></span><span
class="tag">&lt;/logger&gt;</span>
</pre>
<p></p>
<h2>
3. Recommended configuration at
<tt>INFO</tt>
or
<tt>DEBUG</tt>
level, when additionally logging result sets as tables (log4jdbc-remix
feature)
</h2>
This configuration will log all relevant information (SQL statements,
Connection calls, Exceptions thrown), as well as result sets as tables
(log4jdbc-remix feature):
<p></p>
<pre class="prettyprint">
<span class="tag">&lt;logger</span><span class="pln"> </span><span
class="atn">name</span><span class="pun">=</span><span class="atv">"log4jdbc.log4j2"</span><span
class="pln"> </span><span class="atn">level</span><span class="pun">=</span><span
class="atv">"info"</span><span class="pln"> </span><span class="atn">additivity</span><span
class="pun">=</span><span class="atv">"false"</span><span class="tag">&gt;</span><span
class="pln"><br>&nbsp; </span><span class="tag">&lt;MarkerFilter</span><span
class="pln"> </span><span class="atn">marker</span><span class="pun">=</span><span
class="atv">"LOG4JDBC_JDBC"</span><span class="pln"> </span><span
class="atn">onMatch</span><span class="pun">=</span><span class="atv">"</span><span
class="pln">DENY</span><span class="atv">"</span><span class="pln"> </span><span
class="atn">onMismatch</span><span class="pun">=</span><span
class="atv">"</span><span class="pln">NEUTRAL</span><span class="atv">"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; </span><span
class="tag">&lt;appender-ref</span><span class="pln"> </span><span
class="atn">ref</span><span class="pun">=</span><span class="atv">"log4jdbc_file"</span><span
class="tag">/&gt;</span><span class="pln"><br></span><span
class="tag">&lt;/logger&gt;</span>
</pre>
<p></p>
<h2>4. Reproducing standard log4jdbc and log4jdbc-remix behaviors</h2>
Log4jdbc and log4jdbc-remix uses 6 loggers to log different information
(see the log4jdbc documentation). This modified implementation rather
uses
<a rel="nofollow"
href="/web/20160118062235/http://logging.apache.org/log4j/2.0/manual/markers.html">Markers</a>
to achieve the same operations. Here are the configurations to
reproduce the log4jdbc and log4jdbc-remix loggers behaviors:
<ul>
<li><tt>jdbc.sqltiming</tt>: logs SQL statements with execution
time, does not log <tt>Connection</tt> calls, nor JDBC and <tt>ResultSet</tt>
calls.</li>
<p></p>
<pre class="prettyprint">
<span class="pln">&nbsp; &nbsp; </span><span class="tag">&lt;logger</span><span
class="pln"> </span><span class="atn">name</span><span class="pun">=</span><span
class="atv">"log4jdbc.log4j2"</span><span class="pln"> </span><span
class="atn">level</span><span class="pun">=</span><span class="atv">"info"</span><span
class="pln"> </span><span class="atn">additivity</span><span
class="pun">=</span><span class="atv">"false"</span><span
class="tag">&gt;</span><span class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span
class="tag">&lt;MarkerFilter</span><span class="pln"> </span><span
class="atn">marker</span><span class="pun">=</span><span class="atv">"LOG4JDBC_NON_STATEMENT"</span><span
class="pln"> </span><span class="atn">onMatch</span><span
class="pun">=</span><span class="atv">"</span><span class="pln">DENY</span><span
class="atv">"</span><span class="pln"> </span><span class="atn">onMismatch</span><span
class="pun">=</span><span class="atv">"</span><span class="pln">NEUTRAL</span><span
class="atv">"</span><span class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span
class="tag">&lt;appender-ref</span><span class="pln"> </span><span
class="atn">ref</span><span class="pun">=</span><span class="atv">"log4jdbc_file"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;/logger&gt;</span>
</pre>
<li><tt>jdbc.audit</tt>: logs all JDBC calls except for <tt>ResultSet</tt>s.
</li>
<pre class="prettyprint">
<span class="pln">&nbsp; &nbsp; </span><span class="tag">&lt;logger</span><span
class="pln"> </span><span class="atn">name</span><span class="pun">=</span><span
class="atv">"log4jdbc.log4j2"</span><span class="pln"> </span><span
class="atn">level</span><span class="pun">=</span><span class="atv">"info"</span><span
class="pln"> </span><span class="atn">additivity</span><span
class="pun">=</span><span class="atv">"false"</span><span
class="tag">&gt;</span><span class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span
class="tag">&lt;MarkerFilter</span><span class="pln"> </span><span
class="atn">marker</span><span class="pun">=</span><span class="atv">"LOG4JDBC_AUDIT"</span><span
class="pln"> </span><span class="atn">onMatch</span><span
class="pun">=</span><span class="atv">"</span><span class="pln">ACCEPT</span><span
class="atv">"</span><span class="pln"> </span><span class="atn">onMismatch</span><span
class="pun">=</span><span class="atv">"</span><span class="pln">DENY</span><span
class="atv">"</span><span class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span
class="tag">&lt;appender-ref</span><span class="pln"> </span><span
class="atn">ref</span><span class="pun">=</span><span class="atv">"log4jdbc_file"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;/logger&gt;</span>
</pre>
<li><tt>jdbc.resultset</tt>: logs <tt>ResultSet</tt> calls.</li>
<pre class="prettyprint">
<span class="pln">&nbsp; &nbsp; </span><span class="tag">&lt;logger</span><span
class="pln"> </span><span class="atn">name</span><span class="pun">=</span><span
class="atv">"log4jdbc.log4j2"</span><span class="pln"> </span><span
class="atn">level</span><span class="pun">=</span><span class="atv">"info"</span><span
class="pln"> </span><span class="atn">additivity</span><span
class="pun">=</span><span class="atv">"false"</span><span
class="tag">&gt;</span><span class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span
class="tag">&lt;MarkerFilter</span><span class="pln"> </span><span
class="atn">marker</span><span class="pun">=</span><span class="atv">"LOG4JDBC_RESULTSET"</span><span
class="pln"> </span><span class="atn">onMatch</span><span
class="pun">=</span><span class="atv">"</span><span class="pln">ACCEPT</span><span
class="atv">"</span><span class="pln"> </span><span class="atn">onMismatch</span><span
class="pun">=</span><span class="atv">"</span><span class="pln">DENY</span><span
class="atv">"</span><span class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span
class="tag">&lt;appender-ref</span><span class="pln"> </span><span
class="atn">ref</span><span class="pun">=</span><span class="atv">"log4jdbc_file"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;/logger&gt;</span>
</pre>
<li><tt>jdbc.connection</tt>: logs connection calls.</li>
<pre class="prettyprint">
<span class="pln">&nbsp; &nbsp; </span><span class="tag">&lt;logger</span><span
class="pln"> </span><span class="atn">name</span><span class="pun">=</span><span
class="atv">"log4jdbc.log4j2"</span><span class="pln"> </span><span
class="atn">level</span><span class="pun">=</span><span class="atv">"info"</span><span
class="pln"> </span><span class="atn">additivity</span><span
class="pun">=</span><span class="atv">"false"</span><span
class="tag">&gt;</span><span class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span
class="tag">&lt;MarkerFilter</span><span class="pln"> </span><span
class="atn">marker</span><span class="pun">=</span><span class="atv">"LOG4JDBC_CONNECTION"</span><span
class="pln"> </span><span class="atn">onMatch</span><span
class="pun">=</span><span class="atv">"</span><span class="pln">ACCEPT</span><span
class="atv">"</span><span class="pln"> </span><span class="atn">onMismatch</span><span
class="pun">=</span><span class="atv">"</span><span class="pln">DENY</span><span
class="atv">"</span><span class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span
class="tag">&lt;appender-ref</span><span class="pln"> </span><span
class="atn">ref</span><span class="pun">=</span><span class="atv">"log4jdbc_file"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;/logger&gt;</span>
</pre>
<li><tt>jdbc.resultsettable</tt>: Log the jdbc results as a table
(log4jdbc-remix feature). Level debug will fill in unread values in
the result set.</li>
<pre class="prettyprint">
<span class="pln">&nbsp; &nbsp; </span><span class="tag">&lt;logger</span><span
class="pln"> </span><span class="atn">name</span><span class="pun">=</span><span
class="atv">"log4jdbc.log4j2"</span><span class="pln"> </span><span
class="atn">level</span><span class="pun">=</span><span class="atv">"info"</span><span
class="pln"> </span><span class="atn">additivity</span><span
class="pun">=</span><span class="atv">"false"</span><span
class="tag">&gt;</span><span class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span
class="tag">&lt;MarkerFilter</span><span class="pln"> </span><span
class="atn">marker</span><span class="pun">=</span><span class="atv">"LOG4JDBC_RESULTSETTABLE"</span><span
class="pln"> </span><span class="atn">onMatch</span><span
class="pun">=</span><span class="atv">"</span><span class="pln">ACCEPT</span><span
class="atv">"</span><span class="pln"> </span><span class="atn">onMismatch</span><span
class="pun">=</span><span class="atv">"</span><span class="pln">DENY</span><span
class="atv">"</span><span class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span
class="tag">&lt;appender-ref</span><span class="pln"> </span><span
class="atn">ref</span><span class="pun">=</span><span class="atv">"log4jdbc_file"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;/logger&gt;</span>
</pre>
<li><tt>jdbc.sqlonly</tt>: the behavior of this logger is not
implemented. This is for the will of keeping one single logger, while
the logging of events immediately, before the action is executed and
before knowing the execution time, would definitely require another
logger, or a completely different system of Markers. Also, execution
time seems to be an always-useful information to get.</li>
</ul>
<p></p>
<h2>5. Disabling some SQL operations, or dispatching them in
different files</h2>
<p>
The standard implementation of log4jdbc allows to disable the logging
of some SQL operations, through the configuration of log4jdbc
properties (
<tt>log4jdbc.dump.sql.select</tt>
,
<tt>log4jdbc.dump.sql.insert</tt>
,
<tt>log4jdbc.dump.sql.update</tt>
,
<tt>log4jdbc.dump.sql.create</tt>
,
<tt>log4jdbc.dump.sql.delete</tt>
).
</p>
<p>
The same feature is implemented through the use of
<tt>Marker</tt>
s (
<tt>LOG4JDBC_SELECT</tt>
,
<tt>LOG4JDBC_INSERT</tt>
,
<tt>LOG4JDBC_UPDATE</tt>
,
<tt>LOG4JDBC_CREATE</tt>
,
<tt>LOG4JDBC_DELETE</tt>
). This has the advantage to also allow the dispatch of different
operations in different files. Note that the log4jdbc properties can
still be set, and have priority over the
<tt>Marker</tt>
s.
</p>
<p>
Here is an example configuration file to disable the logging of
<tt>select</tt>
operations, while dispatching
<tt>update</tt>
operations in one file, all other statements in another one:
</p>
<p></p>
<pre class="prettyprint">
<span class="pun">&lt;?</span><span class="pln">xml version</span><span
class="pun">=</span><span class="str">"1.0"</span><span class="pln"> encoding</span><span
class="pun">=</span><span class="str">"UTF-8"</span><span class="pun">?&gt;</span><span
class="pln"><br></span><span class="tag">&lt;configuration</span><span
class="pln"> </span><span class="atn">status</span><span class="pun">=</span><span
class="atv">"OFF"</span><span class="tag">&gt;</span><span
class="pln"><br>&nbsp; </span><span class="tag">&lt;appenders&gt;</span><span
class="pln"><br>&nbsp; &nbsp; </span><span class="tag">&lt;Console</span><span
class="pln"> </span><span class="atn">name</span><span class="pun">=</span><span
class="atv">"Console"</span><span class="pln"> </span><span
class="atn">target</span><span class="pun">=</span><span class="atv">"SYSTEM_OUT"</span><span
class="tag">&gt;</span><span class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span
class="tag">&lt;PatternLayout</span><span class="pln"> </span><span
class="atn">pattern</span><span class="pun">=</span><span class="atv">"%d{HH:mm:ss.SSS} [%t] %level - %m%n%ex%n"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;/Console&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;File</span><span class="pln"> </span><span
class="atn">name</span><span class="pun">=</span><span class="atv">"log4jdbc_update"</span><span
class="pln"> </span><span class="atn">fileName</span><span
class="pun">=</span><span class="atv">"log4jdbc_update.out"</span><span
class="tag">&gt;</span><span class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span
class="tag">&lt;MarkerFilter</span><span class="pln"> </span><span
class="atn">marker</span><span class="pun">=</span><span class="atv">"LOG4JDBC_UPDATE"</span><span
class="pln"> </span><span class="atn">onMatch</span><span class="pun">=</span><span
class="atv">"</span><span class="pln">ACCEPT</span><span class="atv">"</span><span
class="pln"> </span><span class="atn">onMismatch</span><span
class="pun">=</span><span class="atv">"</span><span class="pln">DENY</span><span
class="atv">"</span><span class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span
class="tag">&lt;PatternLayout</span><span class="pln"> </span><span
class="atn">pattern</span><span class="pun">=</span><span class="atv">"%d{HH:mm:ss.SSS} [%t] %level - %m%n%ex%n"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;/File&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;File</span><span class="pln"> </span><span
class="atn">name</span><span class="pun">=</span><span class="atv">"log4jdbc_file"</span><span
class="pln"> </span><span class="atn">fileName</span><span
class="pun">=</span><span class="atv">"log4jdbc.out"</span><span
class="tag">&gt;</span><span class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span
class="tag">&lt;MarkerFilter</span><span class="pln"> </span><span
class="atn">marker</span><span class="pun">=</span><span class="atv">"LOG4JDBC_UPDATE"</span><span
class="pln"> </span><span class="atn">onMatch</span><span class="pun">=</span><span
class="atv">"</span><span class="pln">DENY</span><span class="atv">"</span><span
class="pln"> </span><span class="atn">onMismatch</span><span
class="pun">=</span><span class="atv">"</span><span class="pln">NEUTRAL</span><span
class="atv">"</span><span class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span
class="tag">&lt;PatternLayout</span><span class="pln"> </span><span
class="atn">pattern</span><span class="pun">=</span><span class="atv">"%d{HH:mm:ss.SSS} [%t] %level - %m%n%ex%n"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;/File&gt;</span><span class="pln"><br>&nbsp; </span><span
class="tag">&lt;/appenders&gt;</span><span class="pln"><br>&nbsp; </span><span
class="tag">&lt;loggers&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;root</span><span class="pln"> </span><span
class="atn">level</span><span class="pun">=</span><span class="atv">"off"</span><span
class="tag">&gt;</span><span class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span
class="tag">&lt;appender-ref</span><span class="pln"> </span><span
class="atn">ref</span><span class="pun">=</span><span class="atv">"Console"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;/root&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;logger</span><span class="pln"> </span><span
class="atn">name</span><span class="pun">=</span><span class="atv">"log4jdbc.log4j2"</span><span
class="pln"> </span><span class="atn">level</span><span class="pun">=</span><span
class="atv">"info"</span><span class="pln"> </span><span class="atn">additivity</span><span
class="pun">=</span><span class="atv">"false"</span><span class="tag">&gt;</span><span
class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span class="tag">&lt;MarkerFilter</span><span
class="pln"> </span><span class="atn">marker</span><span class="pun">=</span><span
class="atv">"LOG4JDBC_SELECT"</span><span class="pln"> </span><span
class="atn">onMatch</span><span class="pun">=</span><span class="atv">"</span><span
class="pln">DENY</span><span class="atv">"</span><span class="pln"> </span><span
class="atn">onMismatch</span><span class="pun">=</span><span
class="atv">"</span><span class="pln">NEUTRAL</span><span class="atv">"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span
class="tag">&lt;appender-ref</span><span class="pln"> </span><span
class="atn">ref</span><span class="pun">=</span><span class="atv">"log4jdbc_file"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; &nbsp; </span><span
class="tag">&lt;appender-ref</span><span class="pln"> </span><span
class="atn">ref</span><span class="pun">=</span><span class="atv">"log4jdbc_update"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;/logger&gt;</span><span class="pln"><br>&nbsp; </span><span
class="tag">&lt;/loggers&gt;</span><span class="pln"><br></span><span
class="tag">&lt;/configuration&gt;</span>
</pre>
<p></p>
<p>
In a similar way,
<tt>SQLException</tt>
s can be sent to a separate file, using the
<tt>Marker</tt>
<tt>LOG4JDBC_EXCEPTION</tt>
(this is useful when the feature of logging slow queries with an
<tt>ERROR</tt>
level is activated; in this case, an error is not always associated to
an
<tt>Exception</tt>
).
</p>
<p></p>
<p></p>
<hr>
<p></p>
<p></p>
<h1>
Configure a
<tt>DataSource</tt>
</h1>
<h2>Option 1: configure Driver class name and JDBC URL</h2>
<p>
You can either configure your
<tt>DataSource</tt>
to use the log4jdbc-log4j2 driver (<strong><tt>net.sf.log4jdbc.sql.jdbcapi.DriverSpy</tt></strong>),
and to use the modified JDBC URL (prepending <strong><tt>jdbc:log4</tt></strong>
to the normal JDBC URL).
</p>
<p></p>
<p></p>
<h2>
Option 2: wrap into the log4jdbc
<tt>DataSource</tt>
</h2>
<p>
Or you can wrap your own
<tt>DataSource</tt>
into the log4jdbc-log4j2
<tt>DataSource</tt>
. For instance (from the log4jdbc-remix documentation), if you have:
</p>
<pre class="prettyprint">
<span class="pln">&nbsp; </span><span class="tag">&lt;bean</span><span
class="pln"> </span><span class="atn">id</span><span class="pun">=</span><span
class="atv">"dataSource"</span><span class="pln"> </span><span
class="atn">class</span><span class="pun">=</span><span class="atv">"..."</span><span
class="tag">&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;property</span><span class="pln"> </span><span
class="atn">name</span><span class="pun">=</span><span class="atv">"driverClass"</span><span
class="pln"> </span><span class="atn">value</span><span class="pun">=</span><span
class="atv">"${datasource.driverClassName}"</span><span class="tag">/&gt;</span><span
class="pln"><br>&nbsp; &nbsp; </span><span class="tag">&lt;property</span><span
class="pln"> </span><span class="atn">name</span><span class="pun">=</span><span
class="atv">"jdbcUrl"</span><span class="pln"> </span><span
class="atn">value</span><span class="pun">=</span><span class="atv">"${datasource.url}"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;property</span><span class="pln"> </span><span
class="atn">name</span><span class="pun">=</span><span class="atv">"user"</span><span
class="pln"> </span><span class="atn">value</span><span class="pun">=</span><span
class="atv">"${datasource.username}"</span><span class="tag">/&gt;</span><span
class="pln"><br>&nbsp; &nbsp; </span><span class="tag">&lt;property</span><span
class="pln"> </span><span class="atn">name</span><span class="pun">=</span><span
class="atv">"password"</span><span class="pln"> </span><span
class="atn">value</span><span class="pun">=</span><span class="atv">"${datasource.password}"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; ...<br>&nbsp; </span><span
class="tag">&lt;/bean&gt;</span>
</pre>
<p>Change this to</p>
<pre class="prettyprint">
<span class="pln">&nbsp; </span><span class="tag">&lt;bean</span><span
class="pln"> </span><span class="atn">id</span><span class="pun">=</span><span
class="atv">"dataSourceSpied"</span><span class="pln"> </span><span
class="atn">class</span><span class="pun">=</span><span class="atv">"..."</span><span
class="tag">&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;property</span><span class="pln"> </span><span
class="atn">name</span><span class="pun">=</span><span class="atv">"driverClass"</span><span
class="pln"> </span><span class="atn">value</span><span class="pun">=</span><span
class="atv">"${datasource.driverClassName}"</span><span class="tag">/&gt;</span><span
class="pln"><br>&nbsp; &nbsp; </span><span class="tag">&lt;property</span><span
class="pln"> </span><span class="atn">name</span><span class="pun">=</span><span
class="atv">"jdbcUrl"</span><span class="pln"> </span><span
class="atn">value</span><span class="pun">=</span><span class="atv">"${datasource.url}"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;property</span><span class="pln"> </span><span
class="atn">name</span><span class="pun">=</span><span class="atv">"user"</span><span
class="pln"> </span><span class="atn">value</span><span class="pun">=</span><span
class="atv">"${datasource.username}"</span><span class="tag">/&gt;</span><span
class="pln"><br>&nbsp; &nbsp; </span><span class="tag">&lt;property</span><span
class="pln"> </span><span class="atn">name</span><span class="pun">=</span><span
class="atv">"password"</span><span class="pln"> </span><span
class="atn">value</span><span class="pun">=</span><span class="atv">"${datasource.password}"</span><span
class="tag">/&gt;</span><span class="pln"><br>&nbsp; &nbsp; ...<br>&nbsp; </span><span
class="tag">&lt;/bean&gt;</span><span class="pln"><br><br>&nbsp; </span><span
class="tag">&lt;bean</span><span class="pln"> </span><span
class="atn">id</span><span class="pun">=</span><span class="atv">"dataSource"</span><span
class="pln"> </span><span class="atn">class</span><span class="pun">=</span><span
class="atv">"net.sf.log4jdbc.sql.jdbcapi.DataSourceSpy"</span><span
class="tag">&gt;</span><span class="pln"><br>&nbsp; &nbsp; </span><span
class="tag">&lt;constructor-arg</span><span class="pln"> </span><span
class="atn">ref</span><span class="pun">=</span><span class="atv">"dataSourceSpied"</span><span
class="pln"> </span><span class="tag">/&gt;</span><span class="pln"><br>&nbsp; </span><span
class="tag">&lt;/bean&gt;</span>
</pre>
<p></p>
<hr>
<p></p>
<p></p>
<h1>Custom SQL formatter</h1>
<p>
As with log4jdbc-remix, it is possible to provide you own custom log
formatter. Your logger must implement the interface
<tt>net.sf.log4jdbc.log.SpyLogDelegator</tt>
. To make log4jdbc-log4j2 to use it, you have different options:
</p>
<ul>
<li><strong>Option 1</strong> (recommended way): setting the
option <tt>log4jdbc.spylogdelegator.name</tt> to provide the
qualified class name of your implementation of <tt>SpyLogDelegator</tt>.
See below fore more details about setting log4jdbc options.</li>
<li><strong>Option 2</strong>: using the method <tt>net.sf.log4jdbc.log.SpyLogFactory.setSpyLogDelegator(SpyLogDelegator)</tt>
in your application. This method must be called before the loading of
the log4jdbc-log4j2 driver, and thus should be called before any call
to a <tt>DriverManager</tt> or <tt>DataSource</tt>.</li>
<li><strong>Option 3</strong>: using the method <tt>net.sf.log4jdbc.sql.jdbcapi.DataSourceSpy.setLogDelegator(SpyLogDelegator)</tt>
in your application or your <tt>bean</tt> declaration. This method
allows to use different log formatters for different data sources.
Note that you still need to provide a default log formatter (used for
log4jdbc initialization), either by using the default <tt>SpyLogDelegator</tt>
for Log4j 2 (no action required besides installing Log4j 2), or by
configuring through one of the first two options the <tt>SpyLogDelegator</tt>
for SLF4J, or your own custom logger.</li>
</ul>
<p></p>
<p></p>
<p></p>
<hr>
<p></p>
<p></p>
<h1>Configure log4jdbc-log4j2 options</h1>
log4jdbc-log4j2 can be configured in the exact same way than log4jdbc
(see below). Please note two changes as compared to log4jdbc:
<ul>
<li><strong><tt>log4jdbc.spylogdelegator.name</tt>: </strong>this
is a new option, allowing to provide the qualified class name of the
logger to use. Notably, if you want to use the SLF4J logger rather
than Log4j 2, you must set this option to the value <strong><tt>net.sf.log4jdbc.log.slf4j.Slf4jSpyLogDelegator</tt></strong>.</li>
<li><strong><tt>log4jdbc.debug.stack.prefix</tt>: </strong>this
property is now a REGEX, instead of being just the package prefix of
the stack trace. So, for instance, if you want to target the prefix <tt>org.mypackage</tt>,
the value of this property should be: <tt>^org\.mypackage.*</tt>.</li>
</ul>
<p></p>
<p></p>
<h2>Configuration file or System properties</h2>
<p>
From the log4jdbc documentation: you can define any of the log4jdbc
settings either from a file named <strong>log4jdbc.log4j2.properties</strong>
stored in the classpath, or via System properties. log4jdbc will look
for properties both in the configuration file (if it exists) and in
the system properties, with the file taking precedence for any
properties defined in both locations.
</p>
<p></p>
<p></p>
<p>
For instance, if you want to set the option
<tt>log4jdbc.spylogdelegator.name</tt>
, you can either: add to the
<tt>log4jdbc.log4j2.properties</tt>
file:
</p>
<pre class="prettyprint">
<span class="pln">log4jdbc</span><span class="pun">.</span><span
class="pln">spylogdelegator</span><span class="pun">.</span><span
class="pln">name</span><span class="pun">=</span><span class="pln">net</span><span
class="pun">.</span><span class="pln">sf</span><span class="pun">.</span><span
class="pln">log4jdbc</span><span class="pun">.</span><span
class="pln">log</span><span class="pun">.</span><span class="pln">slf4j</span><span
class="pun">.</span><span class="typ">Slf4jSpyLogDelegator</span>
</pre>
<p></p>
<p>Or: use System properties:</p>
<pre class="prettyprint">
<span class="pln">java </span><span class="pun">-</span><span
class="typ">Dlog4jdbc</span><span class="pun">.</span><span
class="pln">spylogdelegator</span><span class="pun">.</span><span
class="pln">name</span><span class="pun">=</span><span class="pln">net</span><span
class="pun">.</span><span class="pln">sf</span><span class="pun">.</span><span
class="pln">log4jdbc</span><span class="pun">.</span><span
class="pln">log</span><span class="pun">.</span><span class="pln">slf4j</span><span
class="pun">.</span><span class="typ">Slf4jSpyLogDelegator</span><span
class="pln"> </span><span class="pun">-</span><span class="pln">classpath </span><span
class="pun">./</span><span class="pln">classes </span><span
class="kwd">my</span><span class="pun">.</span><span class="pln">funky</span><span
class="pun">.</span><span class="typ">Program</span>
</pre>
<p></p>
<p></p>
<p></p>
<h2>log4jdbc-log4j2 options</h2>
<table class="wikitable">
<tbody>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;"><strong>property</strong></td>
<td style="border: 1px solid #ccc; padding: 5px;"><strong>default</strong></td>
<td style="border: 1px solid #ccc; padding: 5px;"><strong>description</strong></td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">log4jdbc.drivers</td>
<td style="border: 1px solid #ccc; padding: 5px;"></td>
<td style="border: 1px solid #ccc; padding: 5px;">One or more
fully qualified class names for JDBC drivers that log4jdbc should
load and wrap. If more than one driver needs to be specified here,
they should be comma separated with no spaces. This option is not
normally needed because most popular JDBC drivers are already
loaded by default-- this should be used if one or more additional
JDBC drivers that (log4jdbc doesn't already wrap) needs to be
included.</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">log4jdbc.auto.load.popular.drivers</td>
<td style="border: 1px solid #ccc; padding: 5px;">true</td>
<td style="border: 1px solid #ccc; padding: 5px;">Set this to
false to disable the feature where popular drivers are
automatically loaded. If this is false, you must set the
log4jdbc.drivers property in order to load the driver(s) you want.</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">log4jdbc.debug.stack.prefix</td>
<td style="border: 1px solid #ccc; padding: 5px;"></td>
<td style="border: 1px solid #ccc; padding: 5px;">A REGEX
matching the package name of your application. The call stack will
be searched down to the first occurrence of a class that has the
matching REGEX. If this is not set, the actual class that called
into log4jdbc is used in the debug output (in many cases this will
be a connection pool class.) For example, setting a system property
such as this: <tt>-Dlog4jdbc.debug.stack.prefix=^com\.mycompany\.myapp.*</tt>
would cause the call stack to be searched for the first call that
came from code in the com.mycompany.myapp package or below, thus if
all of your sql generating code was in code located in the
com.mycompany.myapp package or any subpackages, this would be
printed in the debug information, rather than the package name for
a connection pool, object relational system, etc. <br>
<br> <strong>Please note that the behavior of this
property has changed as compared to the standard log4jdbc
implementation</strong>. This property is now a REGEX, instead of being
just the package prefix of the stack trace. So, for instance, if
you want to target the prefix <tt>org.mypackage</tt>, the value of
this property should be: <tt>^org\.mypackage.*</tt>.
</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">log4jdbc.sqltiming.warn.threshold</td>
<td style="border: 1px solid #ccc; padding: 5px;"></td>
<td style="border: 1px solid #ccc; padding: 5px;">Millisecond
time value. Causes SQL that takes the number of milliseconds
specified or more time to execute to be logged at the warning level
in the sqltiming log. Note that the sqltiming log must be enabled
at the warn log level for this feature to work. Also the logged
output for this setting will log with debug information that is
normally only shown when the sqltiming log is enabled at the debug
level. This can help you to more quickly find slower running SQL
without adding overhead or logging for normal running SQL that
executes below the threshold level (if the logging level is set
appropriately.)</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">log4jdbc.sqltiming.error.threshold
</td>
<td style="border: 1px solid #ccc; padding: 5px;"></td>
<td style="border: 1px solid #ccc; padding: 5px;">Millisecond
time value. Causes SQL that takes the number of milliseconds
specified or more time to execute to be logged at the error level
in the sqltiming log. Note that the sqltiming log must be enabled
at the error log level for this feature to work. Also the logged
output for this setting will log with debug information that is
normally only shown when the sqltiming log is enabled at the debug
level. This can help you to more quickly find slower running SQL
without adding overhead or logging for normal running SQL that
executes below the threshold level (if the logging level is set
appropriately.)</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">log4jdbc.dump.booleanastruefalse
</td>
<td style="border: 1px solid #ccc; padding: 5px;">false</td>
<td style="border: 1px solid #ccc; padding: 5px;">When dumping
boolean values in SQL, dump them as 'true' or 'false'. If this
option is not set, they will be dumped as 1 or 0 as many databases
do not have a boolean type, and this allows for more portable sql
dumping.</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">log4jdbc.dump.sql.maxlinelength
</td>
<td style="border: 1px solid #ccc; padding: 5px;">90</td>
<td style="border: 1px solid #ccc; padding: 5px;">When dumping
SQL, if this is greater than 0, than the dumped SQL will be broken
up into lines that are no longer than this value. Set this value to
0 if you don't want log4jdbc to try and break the SQL into lines
this way. In future versions of log4jdbc, this will probably
default to 0.</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">log4jdbc.dump.fulldebugstacktrace
</td>
<td style="border: 1px solid #ccc; padding: 5px;">false</td>
<td style="border: 1px solid #ccc; padding: 5px;">If dumping in
debug mode, dump the full stack trace. This will result in
EXTREMELY voluminous output, but can be very useful under some
circumstances when trying to track down the call chain for
generated SQL.</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">log4jdbc.dump.sql.select
</td>
<td style="border: 1px solid #ccc; padding: 5px;">true</td>
<td style="border: 1px solid #ccc; padding: 5px;">Set this to
false to suppress SQL select statements in the output. Note that if
you use the Log4j 2 logger, it is also possible to control select
statements output via the marker <tt>LOG4JDBC_SELECT</tt> (see
section "Disabling some SQL operations, or dispatching them in
different files" above). The use of this property prepend the use
of the marker.
</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">log4jdbc.dump.sql.insert
</td>
<td style="border: 1px solid #ccc; padding: 5px;">true</td>
<td style="border: 1px solid #ccc; padding: 5px;">Set this to
false to suppress SQL insert statements in the output. Note that if
you use the Log4j 2 logger, it is also possible to control insert
statements output via the marker <tt>LOG4JDBC_INSERT</tt> (see
section "Disabling some SQL operations, or dispatching them in
different files" above). The use of this property prepend the use
of the marker.
</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">log4jdbc.dump.sql.update
</td>
<td style="border: 1px solid #ccc; padding: 5px;">true</td>
<td style="border: 1px solid #ccc; padding: 5px;">Set this to
false to suppress SQL update statements in the output. Note that if
you use the Log4j 2 logger, it is also possible to control update
statements output via the marker <tt>LOG4JDBC_UPDATE</tt> (see
section "Disabling some SQL operations, or dispatching them in
different files" above). The use of this property prepend the use
of the marker.
</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">log4jdbc.dump.sql.delete
</td>
<td style="border: 1px solid #ccc; padding: 5px;">true</td>
<td style="border: 1px solid #ccc; padding: 5px;">Set this to
false to suppress SQL delete statements in the output. Note that if
you use the Log4j 2 logger, it is also possible to control delete
statements output via the marker <tt>LOG4JDBC_DELETE</tt> (see
section "Disabling some SQL operations, or dispatching them in
different files" above). The use of this property prepend the use
of the marker.
</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">log4jdbc.dump.sql.create
</td>
<td style="border: 1px solid #ccc; padding: 5px;">true</td>
<td style="border: 1px solid #ccc; padding: 5px;">Set this to
false to suppress SQL create statements in the output. Note that if
you use the Log4j 2 logger, it is also possible to control create
statements output via the marker <tt>LOG4JDBC_CREATE</tt> (see
section "Disabling some SQL operations, or dispatching them in
different files" above). The use of this property prepend the use
of the marker.
</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">log4jdbc.dump.sql.addsemicolon
</td>
<td style="border: 1px solid #ccc; padding: 5px;">false</td>
<td style="border: 1px solid #ccc; padding: 5px;">Set this to
true to add an extra semicolon to the end of SQL in the output.
This can be useful when you want to generate SQL from a program
with log4jdbc in order to create a script to feed back into a
database to run at a later time.</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">log4jdbc.spylogdelegator.name</td>
<td style="border: 1px solid #ccc; padding: 5px;">net.sf.log4jdbc.log.log4j2.Log4j2SpyLogDelegator</td>
<td style="border: 1px solid #ccc; padding: 5px;">The qualified
class name of the <tt>SpyLogDelegator</tt> to use. Note that if you
want to use log4jdbc-log4j2 with SLF4J rather than Log4j 2, you
must set this property to: <tt>net.sf.log4jdbc.log.slf4j.Slf4jSpyLogDelegator</tt>.
This is a new property, not present in the standard log4jdbc
implementation.
</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">log4jdbc.statement.warn
</td>
<td style="border: 1px solid #ccc; padding: 5px;">false</td>
<td style="border: 1px solid #ccc; padding: 5px;">Set this to
true to display warnings (Why would you care?) in the log when
Statements are used in the log. NOTE, this was always true in
releases previous to 1.2alpha2. It is false by default starting
with release 1.2 alpha 2.</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">log4jdbc.trim.sql
</td>
<td style="border: 1px solid #ccc; padding: 5px;">true</td>
<td style="border: 1px solid #ccc; padding: 5px;">Set this to
false to not trim the logged SQL. (Previous versions always trimmed
the SQL.)</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">log4jdbc.trim.sql.extrablanklines
</td>
<td style="border: 1px solid #ccc; padding: 5px;">true</td>
<td style="border: 1px solid #ccc; padding: 5px;">Set this to
false to not trim extra blank lines in the logged SQL (by default,
when more than one blank line in a row occurs, the contiguous lines
are collapsed to just one blank line.) (Previous versions didn't
trim extra blank lines at all.)</td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">log4jdbc.suppress.generated.keys.exception
</td>
<td style="border: 1px solid #ccc; padding: 5px;">false</td>
<td style="border: 1px solid #ccc; padding: 5px;">Set to true
to ignore any exception produced by the method,
Statement.getGeneratedKeys() (Useful for using log4jdbc with
Coldfusion</td>
</tr>
</tbody>
</table>
<p></p>
<p>Of note, an additional property allows to set the name of the
property file:</p>
<table class="wikitable">
<tbody>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;"><strong>property</strong></td>
<td style="border: 1px solid #ccc; padding: 5px;"><strong>default</strong></td>
<td style="border: 1px solid #ccc; padding: 5px;"><strong>description</strong></td>
</tr>
<tr>
<td style="border: 1px solid #ccc; padding: 5px;">log4jdbc.log4j2.properties.file
</td>
<td style="border: 1px solid #ccc; padding: 5px;">log4jdbc.log4j2.properties
</td>
<td style="border: 1px solid #ccc; padding: 5px;">Set the name
of the property file to use</td>
</tr>
</tbody>
</table>
<p></p>
<p></p>
<hr>
<p></p>
<p></p>
<h1>Slight modifications as compared to the standard
implementation</h1>
<ul>
<li><strong>connection opening</strong>: if the log4jdbc Driver
is used to acquire the connection to the database, the execution time
to open the connection is now logged. This is not the case if the
connection is opened directly in your code as explained in the <a
rel="nofollow" title="External link to log4jdbc"
href="/web/20160118062235/http://code.google.com/p/log4jdbc/">log4jdbc
FAQ</a>. However, new constructors for <tt>ConnectionSpy</tt> have been
added, allowing to provide this execution time for logging.</li>
<li><strong>connection closing</strong>: time to close the
connection is now always logged.</li>
<li><strong>connection number for statements: </strong>: in
log4jdbc, SQL connection number information is generated to help
identify connection pooling or threading problems. This connection
number was not displayed for logging of SQL statements, now it is.</li>
<li><strong>logging of <tt>getGeneratedKeys()</tt>:
</strong>calls to <tt>getGeneratedKeys()</tt> were not logged as standard SQL
statements, but only as an <tt>audit</tt> information (through the
use of the logger <tt>jdbc.audit</tt>). They are now properly logged,
along with the SQL statement on which they were performed.</li>
<li>Minor changes in line returns or logs presentation. This
might break the scripts provided by log4jdbc to parse the logs.</li>
</ul>
<hr>
<p></p>
<p></p>
<h1>To do</h1>
<ul>
<li>Maybe use the <tt>entry()</tt> and <tt>exit()</tt> methods of
Log4j 2, rather than the <tt>methodReturned()</tt> of the <tt>SpyLogDelegator</tt>.
</li>
</ul>
<p></p>
