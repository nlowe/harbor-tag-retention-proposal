# Proposal: Tag Retention Policies

Author: Nathan Lowe

Last Updated: 2018-09-04

Discussion: [goharbor/harbor#5420](https://github.com/goharbor/harbor/issues/5420)

## Abstract

Provide an automated method of deleting tags from Harbor based on various rules,
which can be defined at the Server, Project, or Repository level. These rules
can be configured by Harbor Admins, or, if enabled, Project Admins.

## Background

Not many people have the luxury of unlimited storage. For images and tags that
are effectively ephemeral (like those built and tagged for use only by an
intermediate process in a CI pipeline) it does not make sense to keep these tags
around for an extended period of time, consuming precious resources. Other tags,
like those correlating to released or deployed software may need to be kept for
an extended period of time or even forever for various legal or compliance
reasons. While this is possible today via Harbor's API, Harbor Administrators
could greatly benefit from having this functionality built-in to harbor itself.

This seems to be a relatively popular issue in the community today:

* [goharbor/harbor#1168](https://github.com/goharbor/harbor/issues/1168) - 强烈建议增加定时删除清理镜像策略 (Google Translate: "It is strongly recommended to add a timed delete cleanup mirroring strategy.")
* [goharbor/harbor#4753](https://github.com/goharbor/harbor/issues/4753) - Can not automation clean old images and can not setup clean policy?
* [goharbor/harbor#5085](https://github.com/goharbor/harbor/issues/5085) - Harbor registry tag cleaner tool

A basic solution exists today as an out-of-tree project contributed by employees
of Hyland Software. For details on this existing solution, please see
[hylandsoftware/Harbor.Tagd](https://github.com/HylandSoftware/Harbor.Tagd).
This solution runs external to Harbor and only supports one type of rule:
"Always keep tags in this list: `[latest, a, b, ...]` and then keep the most recent `x` tags."
These rules cannot be configured from Harbor itself and requires additional
infrastructure to support and run the cleanup process.

## Proposal

[A precise statement of the proposed change.]

## Rationale

[A discussion of alternate approaches and the trade offs, advantages, and disadvantages of the specified approach.]

## Compatibility

[A discussion of the change with regard to the
[compatibility guidelines](https://golang.org/doc/go1compat).]

## Implementation

[A description of the steps in the implementation, who will do them, and when.
This should include a discussion of how the work fits into [Go's release cycle](https://golang.org/wiki/Go-Release-Cycle).]

## Open issues (if applicable)

[A discussion of issues relating to this proposal for which the author does not
know the solution. This section may be omitted if there are none.]