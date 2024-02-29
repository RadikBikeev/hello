pm.test("Status Code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response contains 'data'", function () {
    pm.response.to.have.jsonBody('data');
});

pm.test("Response contains 'auth' in 'data'", function () {
    pm.response.to.have.jsonBody('data.auth');
});

pm.test("Response contains 'timeZone'", function () {
    pm.expect(pm.response.json().hasOwnProperty('time')).to.be.true;
});

pm.test("Store 'timeZone' in variable", function () {
    pm.environment.set('timeZone', pm.response.json().time);
});
