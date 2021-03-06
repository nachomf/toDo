# Installation

## Basic Installation

You can load **TaskProject Application** evaluating:
```smalltalk
Metacello new
	baseline: 'TaskProject';
	repository: 'github://nachomf/TaskProject:master/source';
	load.
```
>  Change `master` to some released version if you want a pinned version

## Using as dependency

In order to include **TaskProject Application** as part of your project, you should reference the package in your product baseline:

```smalltalk
setUpDependencies: spec

	spec
		baseline: 'TaskProject'
			with: [ spec
				repository: 'github://nachomf/TaskProject:v{XX}/source';
				loads: #('Deployment') ];
		import: 'TaskProject'.
```
> Replace `{XX}` with the version you want to depend on

```smalltalk
baseline: spec

	<baseline>
	spec
		for: #common
		do: [ self setUpDependencies: spec.
			spec package: 'My-Package' with: [ spec requires: #('TaskProject') ] ]
```
