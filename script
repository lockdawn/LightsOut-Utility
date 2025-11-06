private _positions = [ 
 [x, y, z],
 [x, y, z]
]; 
 
{ 
    private _pos = _x; 
    { 
        private _type = typeOf _x; 
        if ( 
            (_type find "Lamp") > -1 
            || _type isEqualTo "Land_PowerPoleWooden_L_F" 
            || _type isEqualTo "Land_PowerPoleWooden_F" 
            || _type isEqualTo "Land_PowerPoleWooden_small_F" 
            || _type isEqualTo "Land_FuelStation_01_roof_malevil_F" 
        ) then { 
            _x setDamage 1; 
        }; 
    } forEach (nearestObjects [_pos, [], 600]); 
} forEach _positions; 
