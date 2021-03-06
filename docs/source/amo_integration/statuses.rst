.. _amo-statuses:

===============
Add-on statuses
===============

One can check add-on status in the :ref:`modal-properties` or
:ref:`page-dashboard`.


Every Add-on uploaded to AMO has a status which is one of the following:

* ``STATUS_NULL`` - Incomplete
* ``STATUS_UNREVIEWED`` - (**default**) - Awaiting Preliminary Review
* ``STATUS_PENDING`` - Pending approval
* ``STATUS_NOMINATED`` - Awaiting Full Review
* ``STATUS_PUBLIC`` - Fully Reviewed
* ``STATUS_DISABLED`` - Disabled by Mozilla
* ``STATUS_LISTED`` - Listed
* ``STATUS_BETA`` - Beta
* ``STATUS_LITE`` - Preliminarily Reviewed
* ``STATUS_LITE_AND_NOMINATED`` - Preliminarily Reviewed and Awaiting Full Review
* ``STATUS_PURGATORY`` - Pending a review choice

The AMOStatus needs to be stored (and updated) within
:class:`~jetpack.models.PackageRevision`.

.. note:: Updating PackageRevision status should be done by AMO on every
 status change. AMO should save the
 :attr:`jetpack.models.PackageRevision.pk` and
 :attr:`jetpack.models.Package.pk` with the uploaded Add-on version

Builder adds another statuses:

* ``STATUS_UPLOAD_SCHEDULED`` - Upload scheduled
* ``STATUS_UPLOAD_FAILED`` - Upload failed

If upload finished with success the default AMOStatus will be used. 
