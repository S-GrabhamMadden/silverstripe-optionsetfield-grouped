# Upgrade Guide: Moving to Silverstripe CMS 6

This document outlines the necessary changes to upgrade your project to be compatible with `sunnysideup/optionsetfield-grouped` for Silverstripe CMS 6.

## Core Dependency Updates

⚠️ **BREAKING CHANGE**: This release updates core Silverstripe dependencies. You must update your project's `composer.json` to require the following major versions:

-   `silverstripe/framework`: `^6.0`
-   `silverstripe/admin`: `^3.0`

## API Changes

The following changes were made to align with Silverstripe 6 conventions.

### Namespace Imports

The following `use` statements have been updated to reflect changes in the Silverstripe framework.

-   `SilverStripe\ORM\ArrayLib` has been moved to `SilverStripe\Core\ArrayLib`.
-   `SilverStripe\ORM\ArrayList` has been moved to `SilverStripe\Model\List\ArrayList`.
-   `SilverStripe\View\ArrayData` has been moved to `SilverStripe\Model\ArrayData`.

### PHP `#[Override]` Attribute

⚠️ **BREAKING CHANGE**: To conform with modern PHP standards and Silverstripe 6 practices, the native `#[Override]` attribute has been added to all methods that override a parent implementation in `OptionsetGroupedField.php`. If you have subclassed `OptionsetGroupedField` and overridden any of its methods without using the `#[Override]` attribute, you will need to add it to your method declarations.

The affected methods are:
- `getFieldOption()`
- `Type()`
- `getSourceValues()`
- `performReadonlyTransformation()`
