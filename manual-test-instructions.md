# Manual Testing Instructions for Phone Feature

## Quick Start Tests (5 minutes)

Open `index.html` in your browser and perform these essential tests:

### Test 1: Basic Functionality
1. Open the page
2. Scroll to "Phone number" field
3. **Verify**: Country dropdown shows a country (India or your region)
4. **Verify**: Dropdown shows format like "India (+91)"
5. Select a different country (e.g., "United States (+1)")
6. Type: `555-123-4567`
7. **Verify**: Right panel shows `"phone": "+1 5551234567"` in JSON
8. Switch to "Plain text" tab
9. **Verify**: Shows `Phone: +1 5551234567`

**Expected**: ✅ Phone appears in both outputs with correct format

---

### Test 2: Validation - Invalid Numbers
1. Clear the phone input
2. Type: `123` (only 3 digits)
3. Try to click "Generate resume data" button
4. **Verify**: Browser shows error "must have at least 4 digits"

5. Clear and type: `abc123` (contains letters)
6. Try to submit
7. **Verify**: Error says "only contain digits, spaces, ( ) . -"

**Expected**: ✅ Invalid numbers are rejected with clear error messages

---

### Test 3: 15-Digit Limit
1. Select "India (+91)"
2. Type: `9876543210123` (13 digits)
3. Total = 2 (dial code) + 13 = 15 digits
4. Try to generate
5. **Verify**: NO error (15 is the limit, so it's valid) ✅

6. Add one more digit: `98765432101234` (14 digits)
7. Total = 2 + 14 = 16 digits
8. Try to generate
9. **Verify**: Error says "cannot exceed 15 digits" ✅

**Expected**: ✅ 13 digits accepted, 14 digits rejected with India

---

### Test 4: Save and Restore
1. Select "Canada (+1)"
2. Type: `555-123-4567`
3. Fill in at least Name and Email (required fields)
4. Press F5 to refresh the page
5. **Verify**: Country is still "Canada (+1)" (not United States!)
6. **Verify**: Phone shows `555-123-4567`

**Expected**: ✅ Saved country and number persist after refresh

---

### Test 5: US vs CA Distinction
1. Select "United States (+1)"
2. Enter: `555-999-8888`
3. Fill required fields (name, email)
4. Wait 1 second for auto-save
5. Refresh page (F5)
6. **Verify**: Country is "United States (+1)", NOT "Canada (+1)"

7. Now select "Canada (+1)"
8. Enter: `555-111-2222`
9. Wait 1 second
10. Refresh page
11. **Verify**: Country is "Canada (+1)", NOT "United States (+1)"

**Expected**: ✅ US and CA survive refresh correctly (they both have +1 but are distinguished)

---

### Test 6: Reset Functionality
1. Select a non-default country (e.g., "United Kingdom (+44)")
2. Enter a phone number
3. Click "Reset" button
4. Confirm the reset
5. **Verify**: Country returns to default (India or your region)
6. **Verify**: Phone input is empty
7. **Verify**: No validation errors shown

**Expected**: ✅ Reset restores default country and clears phone

---

### Test 7: Old Format Compatibility
This tests backward compatibility with old saved drafts.

1. Open browser DevTools (F12)
2. Go to Console tab
3. Paste and run this command:
```javascript
localStorage.setItem('resume-json-generator-v1', JSON.stringify({
  personal: {
    fullName: 'Test User',
    email: 'test@example.com',
    phone: '+91 9876543210'
  },
  summary: '',
  education: [],
  skills: [],
  experience: [],
  projects: [],
  certifications: [],
  achievements: [],
  positions: []
}));
```
4. Refresh the page (F5)
5. **Verify**: Page loads without errors
6. **Verify**: Country shows "India (+91)"
7. **Verify**: Phone shows `9876543210`
8. **Verify**: No console errors (check DevTools Console)

**Expected**: ✅ Old draft format loads correctly without errors

---

### Test 8: Responsive Design
1. Make browser window narrow (< 560px wide)
2. **Verify**: Country dropdown is ~110px wide
3. **Verify**: Phone input takes remaining space
4. **Verify**: Layout doesn't break or overflow

5. Make browser window wide (> 900px)
6. **Verify**: Country dropdown is ~124px wide
7. **Verify**: Everything aligns nicely

**Expected**: ✅ Phone field responsive at different screen sizes

---

### Test 9: Theme Switching
1. Phone field should exist in dark theme (default)
2. **Verify**: Select box has dark background and light text
3. **Verify**: Border color matches other inputs

4. Click theme toggle button (sun/moon icon in top right)
5. Switch to light theme
6. **Verify**: Select box has light background and dark text
7. **Verify**: Select styling matches other inputs

**Expected**: ✅ Phone field works in both light and dark themes

---

### Test 10: No Console Errors
1. Open DevTools Console (F12 → Console tab)
2. Refresh page (F5)
3. **Verify**: No red error messages
4. Type in phone field
5. Change country
6. **Verify**: No errors appear

**Expected**: ✅ No console errors during normal operation

---

## All Tests Pass? 🎉

If all 10 tests pass, the phone feature is working correctly!

## Found an Issue?

If any test fails:
1. Note which test failed
2. Note what you expected vs what happened
3. Check browser console for errors
4. Take a screenshot if helpful
