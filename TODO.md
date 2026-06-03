# AniWorld-Downloader Auto-Sync Per-Series Schedule Implementation

## Completed: 2/5

## Steps:
✅ 1. **Edit src/aniworld/web/db.py**: Add `schedule TEXT DEFAULT NULL` to autosync_jobs table with migration logic. Update `update_autosync_job` allowed fields. (Done)

✅ 2. **Edit src/aniworld/web/app.py**: 
   - Update `_autosync_worker()` to use `job.get('schedule') or global_schedule`.
   - Add 'schedule' to `api_autosync_update` allowed fields + validation. (Done)

3. **Edit src/aniworld/web/templates/autosync.html**: Add schedule dropdown (`#editSchedule`) in edit modal, mirroring settings options + "Default" option.

4. **Edit src/aniworld/web/static/autosync.js**: 
   - Add "Schedule" column to table.
   - In openEditModal/saveEdit: handle schedule value.
   - Update computeNextCheck to use job.schedule || global.

5. **Test & Complete**: Restart web UI, verify DB migration, test edit/save per-series schedule, check worker logs/UI next-check computation.

**Next**: Complete step-by-step, update checklist after each.

