# shadowverse-wb-db
Card database for Shadowverse: Worlds Beyond

This contains all cards, including tokens from the **Shadowverse: Worlds Beyond** card game.

## Type definitions

``` typescript
enum CardBooleanRaw {
  true = '1',
  false = '0',
}

enum CardColorRaw {
  abyss = 'Abysscraft',
  dragon = 'Dragoncraft',
  forest = 'Forestcraft',
  haven = 'Havencraft',
  neutral = 'Neutral',
  portal = 'Portalcraft',
  rune = 'Runecraft',
  sword = 'Swordcraft',
}

enum CardSetIdRaw {
  basic = '10000',
  legendsRise = '10001',
  basicToken = '90000',
}

enum CardSetNameRaw {
  basic = 'Basic',
  legendsRise = 'Legends Rise',
  basicToken = 'Basic A',
}

enum CardRarityRaw {
  bronze = '1',
  silver = '2',
  gold = '3',
  rainbow = '4',
}

enum CardTribeRaw {
  Artifact = 'Artifact',
  Mysteria = 'Mysteria',
  Shikigami = 'Shikigami',
  Luminous = 'Luminous',
  Levin = 'Levin',
  Puppetry = 'Puppetry',
  Anathema = 'Anathema',
  Golem = 'Golem',
  Departed = 'Departed',
  Officer = 'Officer',
  EarthSigil = 'Earth Sigil',
  Pixie = 'Pixie',
  Marine = 'Marine',
}

// '4' is equal to 'spell card' in-game
// 'spell' is an amulet in-game which doesn't have a countdown (or has abilities to be engaged)
// 'amulet' is an amulet in-game, which has a countdown
enum CardTypeRaw {
  four = '4',
  amulet = 'Amulet',
  follower = 'Follower',
  spell = 'Spell',
}

// The main card info object in the cards.json array
export interface CardInfoRaw {
  id: string;
  slug: string;
  name: string;
  evo: CardBooleanRaw;
  skill_text: string;
  flavour_text: string;
  class: '0' | '1' | '2' | '3' | '4' | '5' | '6' | '7';
  color: CardColorRaw;
  cv: string;
  evo_skill_text: string | null;
  evo_flavour_text: string | null;
  type: CardTypeRaw;
  cost: '0' | '1' | '2' | '3' | '4' | '5' | '6' | '7' | '8' | '9' | '10' | '18';
  atk: string; // Number, but stored as string
  life: string; // Number, but stored as string
  rarity: CardRarityRaw;
  tribes: CardTribeRaw[];
  setId: CardSetIdRaw;
  set_name: CardSetNameRaw;
  illustrator: string;
  is_token: CardBooleanRaw;
  is_include_rotation: CardBooleanRaw;
  style_card_list:
    | {
        cv: string;
        evo: boolean;
        name: string;
        nonevo: boolean;
        name_ruby: string;
        skill_text: string;
        illustrator: string;
        image_index: number;
        flavour_text: string;
        evo_flavour_text: string;
      }[]
    | null;
  questions: { answer: string; question: string }[];
  related_cards: number[];
  use_red_ether: string | null;
  use_red_ether_foil: string | null;
  get_red_ether: string | null;
  get_red_ether_foil: string | null;
  price: string | null;
  foilPrice: string | null;
  deltaPrice: string | null;
  deltaFoilPrice: string | null;
  delta7dPrice: string | null;
  delta7dPriceFoil: string | null;
  image: string;
  image_back: string | null;
}
```
