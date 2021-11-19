# owsi-maven

This is a maven repository for OWSI-based projects.

## Why?

As no public repository hosts old OWSI pom/jar anymore, we're using GitHub as maven repository in order to be able to continue building old projects relying on old OWSI releases.

## How?

You can change your configuration from:

```xml
<repositories>
	<repository>
		<id>nexus-igloo-releases</id>
		<name>Nexus OWSI Core</name>
		<url>https://nexus.tools.kobalt.fr/repository/igloo-releases/</url>
		<snapshots>
			<enabled>false</enabled>
		</snapshots>
	</repository>
	<repository>
		<id>nexus-igloo-snapshots</id>
		<name>Nexus OWSI Core Snapshots</name>
		<url>https://nexus.tools.kobalt.fr/repository/igloo-snapshots/</url>
		<releases>
			<enabled>false</enabled>
		</releases>
	</repository>
</repositories>
<pluginRepositories>
	<pluginRepository>
		<id>nexus-igloo-releases</id>
		<name>Nexus OWSI Core</name>
		<url>https://nexus.tools.kobalt.fr/repository/igloo-releases/</url>
		<snapshots>
			<enabled>false</enabled>
		</snapshots>
	</pluginRepository>
	<pluginRepository>
		<id>nexus-igloo-snapshots</id>
		<name>Nexus OWSI Core Snapshots</name>
		<url>https://nexus.tools.kobalt.fr/repository/igloo-snapshots/</url>
		<releases>
			<enabled>false</enabled>
		</releases>
	</pluginRepository>
</pluginRepositories>
```

to:

```xml
<repositories>
	<repository>
		<id>github-owsi-maven-releases</id>
		<name>OWSI release dependencies on GitHub</name>
		<url>https://github.com/Smile-SA/owsi-maven/raw/releases/</url>
		<snapshots>
			<enabled>false</enabled>
		</snapshots>
	</repository>
	<repository>
		<id>github-owsi-maven-snapshots</id>
		<name>OWSI snapshot dependencies on GitHub</name>
		<url>https://github.com/Smile-SA/owsi-maven/raw/snapshots/</url>
		<releases>
			<enabled>false</enabled>
		</releases>
	</repository>
</repositories>
<pluginRepositories>
	<pluginRepository>
		<id>github-owsi-maven-releases</id>
		<name>OWSI release dependencies on GitHub</name>
		<url>https://github.com/Smile-SA/owsi-maven/raw/releases/</url>
		<snapshots>
			<enabled>false</enabled>
		</snapshots>
	</pluginRepository>
	<pluginRepository>
		<id>github-owsi-maven-snapshots</id>
		<name>OWSI snapshot dependencies on GitHub</name>
		<url>https://github.com/Smile-SA/owsi-maven/raw/snapshots/</url>
		<releases>
			<enabled>false</enabled>
		</releases>
	</pluginRepository>
<pluginRepositories>
```

Or you can configure a mirror in your ~/.m2/settings.xml:

```xml
<mirror>
        <id>github-owsi-maven-releases/id>
        <mirrorOf>nexus-igloo-releases</mirrorOf>
        <url>https://github.com/Smile-SA/owsi-maven/raw/releases/</url>
</mirror>
<mirror>
        <id>github-owsi-maven-snapshots/id>
        <mirrorOf>nexus-igloo-snapshots</mirrorOf>
        <url>https://github.com/Smile-SA/owsi-maven/raw/snapshots/</url>
</mirror>
```

## Limits

Currently, only versions used by https://github.com/openwide-java/artifact-listener/ project are available in this repository, but others could be added if needed.
