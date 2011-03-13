A collection of patches which have been applied to the Disqus fork of Django.

Please keep in mind that some of these patches are use-case specific, and may have
a better, more generic solution.

Applied Patches:

autocommit_insert.diff
- applies a patch from Django #12180 to fix insert with "returns id" under postgres >= 8.2

delete_related.diff
- adds obj.delete_related() which does django's soft-deleting without deleting the obj itself

improved_natural_keys_13252.diff
- ?

in_bulk_keyiter.diff
- adds back key kwarg to in_bulk and allows anything with __iter__ to be passed in

instance_update.diff
- adds an update() method to model instances which performs atomic updates

psycopg2_safe_close.diff
- overrides connection.close to not error if pgbouncer has already closed the connection for us

send_email_retmsg.diff
- return the messages that are sent when using locmem mail backend

skinnyqueryset_delete_fix.diff
- make QuerySet.delete instantiate a normal QuerySet clone so that it doesn't throw needless SkinnyQuerySet errors

test_constraints.diff
- resolve constraints immediately while testing: http://code.djangoproject.com/ticket/11665
