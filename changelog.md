# Changelog
All notable changes to `cnj-persistence-sql-backend-micro` will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [6.0.0] - 2024-02-28
### Added
- build tags git branch after successful completion
- commit-stage builds produce Docker images for linux/amd64 and linux/arm64/v8 platforms now
- added JSON-B configuration class
- added new unit-test class MessageTest to make sure Jacoco measures test coverage correctly
### Changed
- upgraded Payara to version 6.2024.2
- simplified POM
- consolidated common dependencies
- consolidated common cloudtrain dependencies
- upgraded Java to version 21
- upgraded Maven plugins and dependencies
- build now packages and pushes Helm charts
- deploy now uses packaged Helm charts
- consolidated POM with other showcases
- consolidated system tests with other showcases
- Docker images use Generational Z garbage collector by default
### Fixed
- improved test coverage measurement with Jacoco to include all coverage data in reports
- log messages of test runs are displayed correctly now after upgrade to SLF4J 2.0.9 and using ServiceLoader for log provider lookup
- application logs are actually written to console after (re-)adding dependency slf4j-jdk14

## [5.1.0] - 2023-08-25
### Added
- added explicit dependency to CloudTrain Maven repository to POM to simplify local builds
- allowed anonymous read access to CloudTrain Maven repository to simplify local builds
- added global docker-compose.yml file to simplify local execution
### Changed
- improved documentation in README.md

## [5.0.0] - 2023-06-07
### Changed
- moved to new AWS CodeBuild build pipeline
- moved to new CloudTrain EKS cluster
- upgraded everything

## [4.1.0] - 2022-09-13
### Added
### Changed
- re-released after repo split
- consolidated with other MicroProfile show cases
